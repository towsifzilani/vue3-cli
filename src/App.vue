<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <h1>{{ title }}</h1>
  <input type="text" ref="name">
  <button @click="handleClick">Click Me</button>
  <br>
  <br>
  <teleport to="#modals" v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links>
          <a href="#">Sign up</a>
          <a href="#">Sign in</a>
      </template>
      <h1>Hurrah! You are right there</h1>
      <p>Enjoy your holidays with joy and peace...</p>

    </Modal>
  </teleport>
  <br>
  <br>
  <div v-if="showModalTwo">
    <Modal theme="sale" @close="toggleModalTwo">
      <template v-slot:links>
          <a href="#">Sign up now</a>
          <a href="#">Read more</a>
      </template>
      <h1>Hurrah! You are right there</h1>
      <p>Enjoy your holidays with joy and peace...</p>

    </Modal>
  </div>
  <button @click="toggleModal">Open Modal (shift key)</button>
  <button @click="toggleModalTwo">Open Another Modal</button>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Modal from './components/Modal.vue'
import './assets/css/global.css'

export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: "My First Vue Project",
      header: "This is header content",
      content: "This is body content",
      showModal: false,
      showModalTwo: false,
    }
  },
  methods: {
    handleClick() {
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()
    },
    toggleModal() {
      this.showModal=!this.showModal
    },
    toggleModalTwo() {
      this.showModalTwo=!this.showModalTwo
    }
  }
}
</script>

<style>

#app, .modal {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

</style>
