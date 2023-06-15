<template>
  <section class="hero">
    <Header></Header>
    <div class="hero__info">
      <h1 class="hero__title">
        Blog
      </h1>
      <p class="hero__subtitle">
        Our blog is a huge universe of stories and ideas of many people from all over the world.
      </p>
    </div>
  </section>
  <main class="main">
    <section class="post-content">

    </section>
  </main>
  <Footer></Footer>
</template>

<script>
import Header from "@/components/Header.vue";
import Footer from "@/components/Footer.vue";
import IconLogo from "@/components/icons/IconLogo.vue";
export default {
  components: {Header, Footer, IconLogo}

}
</script>

<style scoped>

</style>