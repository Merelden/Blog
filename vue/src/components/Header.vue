<template>
  <header class="header">
    <div class="header__content">
      <nav class="header__nav">
        <router-link class="header__link" to="/">Home</router-link>
        <router-link class="header__link" to="/blog">Blog</router-link>
      </nav>
      <router-link to="/">
        <IconLogo></IconLogo>
      </router-link>
      <button class="header__login btn" @click="modalLogin.show = !modalLogin.show">Login</button>
    </div>
  </header>
  <modals
      title="Login"
      v-show="modalLogin.show"
      @close="modalLogin.show = false"
      :isOpen="modalLogin.show"
  >
      <template v-slot:body>
        <form>
          <div class="form-item" :class="{ error: v$.form.email.$errors.length }">
            <label>Login:</label>
            <input type="email" placeholder="Enter your name"  v-model="v$.form.email.$model">
            <div class="input-errors" v-for="(error, index) of v$.form.email.$errors" :key="index">
              <p class="error-msg">{{ error.$message() }}</p>
            </div>
          </div>
          <div class="form-item" :class="{ error: v$.password.$errors.length }">
            <label>Password:</label>
            <input type="password" placeholder="Enter your password" v-model="v$.form.password.$model">
            <div class="input-errors" v-for="(error, index) of v$.form.password.$errors" :key="index">
              <p class="error-msg">{{ error.$message() }}</p>
            </div>
          </div>
          <button class="btn" :disabled="v$.form.$invalid">Sign in</button>
        </form>
      </template>
  </modals>
</template>

<script>
import IconLogo from "@/components/icons/IconLogo.vue";
import modals from "@/components/UI/LoginModal.vue";
import { required, minLength } from '@vuelidate/validators'
import useVuelidate from '@vuelidate/core'

export default {
  name: "Header",
  components: {IconLogo, modals},
  data() {
    return {
      modalLogin: {
        show: false,
      },
      form: {
        email: '',
        password: ''
      }
    }
  },
  setup () {
    return { v$: useVuelidate() }
  },
  validations () {
    return {
      form: {
        email: {
          required, email
        },
        password: {
          required,
          min: minLength(6)
        }
      }
    }
  }
}
</script>

<style scoped>

.header {
  z-index: 2;
  position: absolute;
  width: 1700px;
}

.header__nav {
  display: flex;
  gap: 55px;
}

.header__content {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.header__login {
  border: none;
  outline: none;
}

</style>