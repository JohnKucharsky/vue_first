<template>
  <h1>
    {{ title }}
  </h1>
  <div v-if="showModal">
    <ModalComponent theme="sale" @close="toggleModal">
      <h1>Ninja Giveway!</h1>
      <p>Grab your ninja swag for half price!</p>
      <template v-slot:links>
        <a href="#">sign up now</a>
        <a href="#">more info</a>
      </template>
    </ModalComponent>
  </div>
  <div v-if="showModalTwo">
    <ModalComponent @close="toggleModalTwo">
      <p>For updates and promocodes</p>
      <h1>Sign up to the newsletter</h1>
    </ModalComponent>
  </div>
  <button @click="toggleModal">open modal</button>
  <button @click="toggleModalTwo">open modal two</button>
</template>

<script>
import ModalComponent from "./components/ModalComponent.vue";
export default {
  name: "App",
  components: {
    ModalComponent,
  },
  data() {
    return {
      showModal: false,
      showModalTwo: false,
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo;
    },
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
input {
  padding: 0.3rem;
}
h1 {
  color: teal;
}
</style>
