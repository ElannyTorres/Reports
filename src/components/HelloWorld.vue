<template>
  <div class="container">
    <h1>{{ msg }}</h1>
    <ReportsRecord>
    </ReportsRecord>
    <ModalView v-if="showModal">
      <button id="close" @click="closeModal">
        Cancelar
      </button>
    </ModalView>
    <button  @click="openModal">
      Crear reporte
    </button>
  </div>
</template>

<!-- :reports="reports" -->

<script>
  import ReportsRecord from './Reports.vue';
  import ModalView from './Modal.vue';

  export default {
    name: 'HelloWorld',
    data(){
      return {
        showModal: false,
      }
    },
    props: {
      msg: String
    },
    components: {
      ReportsRecord,
      ModalView
    },
    methods: {
      openModal() {
        this.showModal = true;
      },
    closeModal() {
      this.showModal = false;
    }
    }
  };
</script>


<style scoped>
  .container {
    margin: 0;
    padding: 1rem;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  button {
    background-color: #FFBE12;
    border-radius: 1rem;
    border: none;
    padding: 0.5rem;
    width: 8rem;
    box-shadow: 1px 1px 1px 1px grey;
    cursor: pointer;
  }
  #close {
    margin: 1px;
    margin-top: 1rem;
  }
</style>
