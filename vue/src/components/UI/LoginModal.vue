<template>
  <transition name="modal">
    <div v-if="isOpen" class="modal__wrapper" @click="$emit('close')">
      <div class="modal-content" @click.stop="">

        <div class="modal-header">
          <h1 class="modal-title">
            {{ title }}
          </h1>
          <span class="button-close" @click="$emit('close')">x</span>
        </div>

        <div class="modal-body">
          <slot name="body"> Default body </slot>
        </div>
      </div>
    </div>
  </transition>
</template>

<script>
export default {
  name: "LoginModal",
  props: {
    title: {
      type: String,
      required: true
    },
    body: {
      type: Object,
      required: true
    }
  },
  data() {
    return {
      isOpen: true,
      modalLogin: {
        show: false,
        login: '',
        password: ''
      },
      modalRegistration: {
        show: false,
        login: '',
        password: ''
      }
    }
  },
  mounted() {
    document.addEventListener('keydown', this.handleKeyDown);
  },
  destroyed() {
    document.removeEventListener('keydown', this.handleKeyDown)
  },
  computed: {},
  methods: {
    handleKeyDown(event) {
      if (event.keyCode === 27) {
        this.$emit('close')
      }
    }
  }
}
</script>

<style lang="css" scoped>
.modal-enter, .modal-leave-active {
  opacity: 0;
}

.modal-enter .modal-content,
.modal-leave-active .modal-content {
  transform: scale(1.2);
}

.modal__wrapper {
  display: flex;
  justify-content: center;
  align-items: center;
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  transition: opacity .4s ease;
  right: 0;
  z-index: 998;
  background-color: rgba(00, 00, 00, .48);
}

.modal-content {
  position: relative;
  min-width: 600px;
  padding: 20px 18px;
  background-color: #fff;
  border: 1px solid #dcdfe6;
  transition: all .2s ease;
  border-radius: 8px;
  z-index: 999;
  overflow: hidden;
}

.modal-header {
  display: flex;
  justify-content: space-between;
  padding-bottom: 20px;
}

.button-close {
  cursor: pointer;
}

.modal-body {
  display: flex;
  flex-direction: column;
  gap: 15px;
}

</style>