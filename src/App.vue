<template>
  <div>
    <h1>{{ title }}</h1>
    <p>W e l c o m e  .  .  .</p>
    <teleport to=".modals" v-if="showModal">
      <!-- <Modal :header="header" :text="text" theme="sale" @close="toggleModal"/> -->
      <Modal theme="sale" @close="toggleModal">
        <template v-slot:links>
          <div>
            <a href="#">sign up now</a>
            <a href="#">more info</a>
            
          </div>
        </template>
        <h1>Sign up for the Giveaway!</h1>
        <p>Hurry and Grab Your Offer while stock lasts</p>
      </Modal>
    </teleport>
    <button @click.alt="toggleModal">open Modal (alt)</button>

    <div v-if="showModalTwo">
      <Modal @close="toggleModalTwo">
        <template v-slot> 
          <h1>Sign up to the newsletter </h1>
          <p>For more updates and Promo codes!</p>
          <div>
            <a href="#">Home</a>

            
          </div>
        </template>
      </Modal>

    </div>
    <button @click="toggleModalTwo">open Modal 2</button>
    
    <!-- <input type="text" ref="name">
    <button @click="handleClick">click me</button> -->
  </div>  
</template>

<script>
/**
 * Challenge
 *    - Create an extra button to open a different modal
 *    - use the same modal component but pass in a different template (slot)
 *    - use a different method (e.g. toggleModalTwo) and data (e.g. showModalTwo)
 */

import Modal from './components/Modal.vue'


export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title:'My First Vue App',
      header: 'Sign up for the Giveaway!',
      text: 'Hurry and Grab Your Offer while stock lasts',
      showModal: false,
      showModalTwo: false,
    }
  },
  methods: {
    toggleModal(){
      this.showModal = !this.showModal
    },
    toggleModalTwo() {
        this.showModalTwo = !this.showModalTwo
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
