<template>
  <h1>{{title}}</h1>
  <p>Welcome...</p>
  <teleport to="#modals" v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">sign up now</a>
        <a href="#">more info</a>
      </template>
      <h1>Super Giveaway</h1>
      <p>Grab your swag!</p>
    </Modal>
  </teleport>

  <teleport to="#modals" v-if="showModal2">
    <Modal @close="toggleModal2">
      <h1>Crazy</h1>
      <p>Modal stuff!</p>
    </Modal>
  </teleport>
  <button @click.alt="toggleModal">Open modal (alt)</button>
  <button @click="toggleModal2">Open modal2</button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: {
    Modal
  },
  data() {
    return {
      title: "My First View App :D",
      header: "Sign up for the Giveaway!",
      text: "Cool stuff for half price!",
      showModal: false,
      showModal2: false,
    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    },
    toggleModal2() {
      this.showModal2 = !this.showModal2
    }
  },
 }
</script>

<style>
#app, #modals {
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
