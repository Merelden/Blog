<template>
<div class="modal__wrapper">
  <div class="modal-content">
    <div class="modal-header">
      <h1 class="modal-title">
        {{ title }}
      </h1>
      <span class="modal-close">
         &times;
      </span>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: "LoginModal",
  data() {
    return {
      modalFirst: false
    }
  },
  props: {
    title: {
      type: String,
      required: true
    }
  },
  computed: {},
  methods: {}
}
</script>

<style scoped>

</style>