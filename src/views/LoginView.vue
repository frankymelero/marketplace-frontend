<script setup>


</script><template>
  <PublicMenu />
  <div class="about">
    <div class="login-form">
      <h1>Login</h1>
      <form @submit.prevent="handleLogin">
        <label for="username">Usuario</label><br />
        <input type="text" ref="usernameInput" v-model="state.username" name="username" placeholder="Introduce el usuario" required/><br />
        <label for="password">Contraseña</label><br />
        <input type="password" ref="passwordInput" v-model="state.password" name="password" placeholder="Introduce la contraseña" required/><br /><br />
        <button type="submit" @click="handleApiCall">Enviar</button>
        <p>
          ¿No tienes cuenta? <RouterLink to="/register">Registrate</RouterLink>
        </p><br/>
        (testing) Usuario => {{  state.username }}
      </form>
    </div>
  </div>
</template>
<script>
import { reactive, ref } from 'vue';
import { RouterLink } from 'vue-router';
import router from '../router/index.js';
import PublicMenu from '../components/PublicMenu.vue';

export default {
  components: { RouterLink, PublicMenu },
  setup() {
    const state = reactive({
      username: '',
      password: '',
    });
    const usernameInput = ref(null);
    const passwordInput = ref(null);
    
    const handleLogin = async () => {
  if (!state.username || !state.password) {
    alert('Por favor, introduce un nombre de usuario y una contraseña.');
    return;
  }

  const url = `http://127.0.0.1:8080/users/validation/${state.username}/${state.password}`;
  try {
    const response = await fetch(url);
    if (response.status === 200) {
      const data = await response.json();
      localStorage.setItem('username', state.username);
      localStorage.setItem('logged', "si");
      localStorage.setItem('id', data.id);
      router.push('/home');
    } else {
      alert('Usuario o contraseña incorrectos');
    }
  } catch (error) {
    console.error(error);
    alert('Ha ocurrido un error. Por favor, intenta nuevamente.');
  }
};
     const handleApiCall = (event) => {
      event.preventDefault();
      console.log(`Usuario: ${state.username}`);
      console.log(`Usuario: ${state.username}`);
      handleLogin();
    };
    
    return {
      state, 
      usernameInput,
      passwordInput,
      handleApiCall,
    };
  },
};
</script>



<style scoped>
.about {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.login-form {
  background-color: #ffffff;
  padding: 40px;
  border-radius: 5px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.507);
  max-width: 400px;
  width: 100%;
}

.login-form h1 {
  text-align: center;
  font-size: 2rem;
  margin-bottom: 20px;
}

.login-form label {
  display: block;
  font-size: 1.2rem;
  margin-bottom: 5px;
}

.login-form input[type="text"],
.login-form input[type="password"] {
  width: 100%;
  padding: 10px;
  margin-bottom: 20px;
  font-size: 1rem;
  border: 2px solid #cccccc;
  border-radius: 5px;
}

.login-form input[type="submit"] {
  background-color: #614caf;
  color: white;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 1.2rem;
}

.login-form input[type="submit"]:hover {
  background-color: #3e7b8e;
}

.login-form p {
  margin-top: 20px;
  font-size: 1.2rem;
  text-align: center;
}

.login-form p a {
  color: #664caf;
}

</style>

