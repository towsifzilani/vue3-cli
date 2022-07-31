<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <h1>{{ title }}</h1>
  <input type="text" ref="name">
  <button @click="handleClick">Click Me</button>
  <br>
  <br>
  <div v-if="showModal">
    <Modal :header="header" :content="content" theme="sale" @close="toggleModal"/>
  </div>
  <button @click="toggleModal">Open Modal</button>
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
      showModal: false
    }
  },
  methods: {
    handleClick() {
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()
    },
    toggleModal() {
      this.showModal=!this.showModal
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
