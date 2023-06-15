<template>
  <div class="main">
    <section class="hero">
      <Header></Header>
      <div class="hero__info">
        <h1 class="hero__title">
          Hey, we`re Paradise. See your
          thoughts, stories and ideas.
        </h1>
        <p class="hero__subtitle">
          Paradise is minimal multipurpose blog. A beautiful way to share stories with growing audience.
        </p>
      </div>
    </section>
    <section class="popular">
      <div class="wrapper">
        <div class="popular__header">
          <h1 class="popular__header-title">
            Popular posts
          </h1>
          <router-link to="" class="popular__header-btn btn">
            View all
          </router-link>
        </div>
        <div class="popular__content">
          <div class="popular__post">
            <img src="./src/assets/img/post.png" alt="post" class="popular__post-img">
            <h3 class="popular__post-title">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ipsa, maiores?</h3>
            <p class="popular__post-text">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dolorem error harum itaque quis similique velit.</p>
            <p class="popular__post-date">17.03.2023</p>
          </div>
          <div class="popular__post">
            <img src="./src/assets/img/post.png" alt="post" class="popular__post-img">
            <h3 class="popular__post-title">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ipsa, maiores?</h3>
            <p class="popular__post-text">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dolorem error harum itaque quis similique velit.</p>
            <p class="popular__post-date">17.03.2023</p>
          </div>
          <div class="popular__post">
            <img src="./src/assets/img/post.png" alt="post" class="popular__post-img">
            <h3 class="popular__post-title">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ipsa, maiores?</h3>
            <p class="popular__post-text">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dolorem error harum itaque quis similique velit.</p>
            <p class="popular__post-date">17.03.2023</p>
          </div>
        </div>
      </div>
    </section>
    <section class="modal">
      <div class="container">
<!--        <modals title="Login"-->
<!--        v-if="modalFirst = !modalFirst" >-->
<!--        </modals>-->
      </div>
    </section>
    <Footer></Footer>
  </div>
</template>

<script>
import Header from "@/components/Header.vue";
import Footer from "@/components/Footer.vue";
export default {
  components: {Header, Footer},
}
</script>

<style scoped>

</style>