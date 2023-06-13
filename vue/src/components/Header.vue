<template>
  <header class="header">
      <div class="header__content">
        <nav class="header__nav">
          <router-link class="header__link" to="/">Home</router-link>
          <router-link class="header__link" to="/blog">Blog</router-link>
        </nav>
        <router-link to="/"><IconLogo></IconLogo></router-link>
        <router-link class="header__login btn" to="/" @click="">Login</router-link>
      </div>
  </header>
</template>

<script>
import IconLogo from "@/components/icons/IconLogo.vue";
import modals from "@/components/LoginModal"
export default {
  name: "Header",
  components: {IconLogo, modals}
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

</style>