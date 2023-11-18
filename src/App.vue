//learning about slots - they are used to decrease the use of props and make the
working of components more dynamic

//Insted of passing the the data inside the Modal div to the Modal
      componenet,we are doing it here and send the data as a slot in the
      modal component
<template>
  <h1>{{ title }}</h1>

  <div v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">Sign up</a>
      </template>
      <h1>10% off on Indri!</h1>
      <p>Grab your bottle today!!</p>
    </Modal>
  </div>
  <br>
  <div v-if = "showModal2">
    <Modal theme = "sale" @close = "toggleModal2">
      <template v-slot: second>
        <h1>20% off on Royal Stag!</h1>
        
      </template>
    </Modal>
  </div>
  <button @click="toggleModal">Show modal</button>
  <button @click = "toggleModal2">Show Modal 2</button>
</template>

<script>
import Modal from "./components/Modal";

export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "My First Vue App!",
      header: "10% off on Indri!",
      text: "Grab it before anyone else!",
      showModal: false,
      showModal2: false
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleModal2() {
      this.showModal2 = !this.showModal2

    }
  },
};
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

h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
