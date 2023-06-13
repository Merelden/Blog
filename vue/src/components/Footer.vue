<template>
  <footer class="footer">
    <div class="footer__content">
      <nav class="footer__nav">
        <router-link to="/Home.vue">Home</router-link>
        <router-link to="/Blog.vue">Blog</router-link>
      </nav>
      <IconLogo></IconLogo>
      <div class="footer__rights">
        <p class="footer__rights-text">
          © 2023 Dribbble. All rights reserved.
        </p>
      </div>
    </div>
  </footer>
</template>

<script>
import IconLogo from "@/components/icons/IconLogo.vue";

export default {
  name: "Footer",
  components: {IconLogo}

}
</script>

<style scoped>

.footer {
  display: flex;
  justify-content: center;
  background-image: url("../assets/img/Footer.png");
}

.footer__content {
  display: flex;
  justify-content: space-between;
  align-items: center;
  max-width: 1700px;
  width: 100%;
}

.footer__nav {
  display: flex;
  gap: 55px;
}

</style>