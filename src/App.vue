<template>
  <div v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <!--Named slot template-->
      <template v-slot:namedSlot> 
        <a href="#">Inside the named slot</a>
      </template>
      <!--Default slot content-->
      <h1>Title for default slot</h1>
      <p>This is the default slot content</p>
    </Modal>
  </div>

  <div v-if="showModalTwo">
    <Modal theme="sale" @close="toggleModalTwo">
      <!--Named slot template-->
      <template v-slot:namedSlot> 
        <a href="#">Inside the named slot</a>
      </template>
      <!--Default slot content-->
      <h1>This is the second slot</h1>
      <p>This is the default slot content</p>
    </Modal>
  </div>
  
  <button @click="toggleModal">Open Modal</button><br><br>
  <button @click="toggleModalTwo">Open Second Modal</button>
</template>

<script>

import Modal from './components/Modal.vue'


export default {
  name: 'App',
  
  components: { Modal },
  data(){
    return {
      showModal: false,
      showModalTwo: false
    }
  },
  methods:{
    toggleModal(){
      this.showModal = !this.showModal
    },
    toggleModalTwo(){
      this.showModalTwo = !this.showModalTwo
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
