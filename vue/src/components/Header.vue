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
      <button class="header__login btn" @click="modalLogin = !modalLogin">Login</button>
    </div>
  </header>
  <modals
      title="Login"
      v-show="modalLogin"
      @close="modalLogin = false"
  >

  </modals>
</template>

<script>
import IconLogo from "@/components/icons/IconLogo.vue";
import modals from "@/components/LoginModal.vue";

export default {
  name: "Header",
  components: {IconLogo, modals},
  data() {
    return {
      modalLogin: false
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
}

</style>