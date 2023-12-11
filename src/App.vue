<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <div id="appVue" @Load="submitToShowModal">
    <h1>{{  title  }}</h1>
    <Modal v-if="propOpenModal" :title="modalTitle" :message="modalMessage" :showButton="modalWithButton"/>
</div>
</template>

<script>
import  Modal  from "./components/Modal.vue"

export default {
  name: 'App',
  data() {
      return {
          title: "Books List",
          message: "Modal prompt to be shown",
          modalTitle: "Do you have a book in mind?",
          modalMessage: "I know you have books in shelf and not in mind",
          modalVue: true,
          modalWithButton: true,
          propOpenModal: false
      }
  },
  components : {
    Modal
  },
  mounted() {
    this.submitToShowModal();
  },
  methods: {
    handleRefs(){
      this.$refs.name.classList.add("app");
      this.$refs.name.focus();
    },
    showModal() {
      this.propOpenModal = !this.propOpenModal ;
    },
    modalActions() {
      console.log("Modal actions"+this.Modal.closeModal());
    },
    submitToShowModal() {
      console.log("Submitting to show");
      setTimeout(
        this.showModal ,10000);
    }


  }

}
</script>
<style>
  #app{
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
  h1{
    border-bottom-width: 0px;
  }
</style>