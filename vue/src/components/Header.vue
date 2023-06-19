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
      <button class="header__login btn" @click="modalLogin.show = !modalLogin.show">Register</button>
      <button class="header__login btn" @click="modalRegistration.show = !modalRegistration.show">Sign In</button>
    </div>
  </header>
  <modals
      title="Login"
      v-show="modalLogin.show"
      @close="modalLogin.show = false"
      :isOpen="modalLogin.show"
  >
      <template v-slot:body>
        <form class="form-modal">
          <div class="form-item">
            <input type="email" placeholder="Enter your name" class="form-input">
          </div>
          <div class="form-item">
            <input type="password" placeholder="Enter your password" class="form-input">
          </div>
          <button class="btn">Sign in</button>
        </form>
      </template>
  </modals>
  <modals
    title="Registration"
    v-show="modalRegistration.show"
    @close="modalRegistration.show = false"
    :isOpen="modalRegistration.show"
  >
      <template v-slot:body>
        <form class="form-modal">

        </form>
      </template>
  </modals>
</template>

<script>
import IconLogo from "@/components/icons/IconLogo.vue";
import modals from "@/components/UI/LoginModal.vue";

export default {
  name: "Header",
  components: {IconLogo, modals},
  data() {
    return {
      modalLogin: {
        show: false,
      },
      modalRegistration: {
        show: false
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

.form-modal {
  display: flex;
  flex-direction: column;
  gap: 15px;
}

.form-input {
  padding: 10px 20px;
  border-radius: 10px;
  border: 2px solid #919191;
  outline: none;
  cursor: pointer;
}
.form-input:hover {
  border: 2px solid black;
}


</style>