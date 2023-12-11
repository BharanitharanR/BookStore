<template>
    <div class="backdrop" v-if="showModal">
        <div class="modal" >
            <h1>{{  title }}</h1>
            <p> {{ message }}</p>
            <button v-if="showButton">
                Close 
            </button>
        </div>
    </div>
</template>
<script>
export default {
    name: 'Modal',
    props: ["title","message","theme","showButton","buttonText"],
    data() {
      return {          
          showModal: true
      }
    },
    method: {
        closeModal() {
            console.log("close within modal" + this.showModal);
            this.showModal = !this.showModal;
        }
    }
} 
</script>
<style>
.backdrop{
    top: 0;
    position: fixed;
    background: rgba(0, 0, 0,0.5);
    width: 100%;
    height: 100%;
}
.modal{
    width: 400px;
    padding: 20px;
    background-color: rgb(240, 234, 234);
    margin: 150px auto;
    border-radius: 10px;
}
.modal h1{
    font-style: normal;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}
</style>