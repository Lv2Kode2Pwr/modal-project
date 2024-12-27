<template>
  <h1>{{ title }}</h1>
  <p>Welcome...</p>
  <teleport to=".modals" v-if="showModal">
    <Modal theme=""  @close="toggleModal">
      <h1>Ninja Giveaway!</h1>
      <p>Grab your ninja swag for half price!</p>
      <template v-slot:links>
        <a href="#">sign up now   </a>
        <a href="#">more info</a>
      </template>
    </Modal>
  </teleport>
  
  <teleport to=".modals" v-if="showModal2">
    <Modal @close="toggleModal2">
      <h1>Sign up to the newsletter</h1>
      <p>For updates and promo codes!</p>
    </Modal>
  </teleport>
  <button @click.alt='toggleModal'>Open modal (alt)</button>
  <p>Welcome again...</p>
  <button @click.ctrl='toggleModal2'>Open modal (ctrl)</button>
  <!-- <HelloWorld /> -->
</template>

<script>
import Modal from './components/Modal.vue'
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    Modal    // HelloWorld
  },
  data() {
    return {
      title: "My First Vue App :)",
      showModal: false,
      showModal2: false
    }
    },
    methods: {
      toggleModal() {
        this.showModal = !this.showModal
    },
    toggleModal2() {
      this.showModal2 = !this.showModal2
    }
  }
}

</script>

<style>
#app, .modals {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
