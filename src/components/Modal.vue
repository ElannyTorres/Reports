<template>
  <div class="container">
    <form class="modal" @submit="generarReporte">
      <h2>
        <strong>Reporte por fecha de nacimiento</strong>
      </h2>
      <p>Ingresa los siguientes datos para generar tu reporte</p>
      <label>
        Descripción del reporte
      </label>
      <br>
      <input type="text"
        v-model="fileName"
      />
      <p>Fecha de nacimiento</p>
      <div class="date">
        <div class="info">
          <label>
            Inicio
          </label>
          <br>
          <input type="date"
            v-model="startDate"
          />
        </div>
        <div class="info">
          <label>Fin</label>
          <br>
          <input type="date"
            v-model="endDate"
          />
        </div>
      </div>
      <div class="btns">
        <button type="submit"
          :disabled="false">
          Generar reporte
        </button>
        <slot />
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: 'ModalView',
  data() {
    return {
      fileName: '',
      startDate: '',
      endDate: '',
      newReport: {}
    }
  },
  methods: {
    generarReporte() {
      this.newReport = {
        fileName: this.fileName,
        startDate: this.startDate,
        endDate: this.endDate,
        date: new Date().toLocaleDateString()
      }
      console.log(this.newReport);
      localStorage.setItem('newReports', JSON.stringify(this.newReport));
      return this.newReport;
    },
    btnReport(){
      let isDisabled = true;
      console.log(this.fileName);
      if (
        this.fileName !== ''
      ) {
        isDisabled = false;
      } else {
        isDisabled = true;
      }
      return isDisabled;
    }
  },
  mounted() {
    this.$emit('nuevoReporte', this.newReport);
  }
};
</script>

<style scoped>

  .container {
    margin: 0;
    padding: 0;
    background-color: rgba(0, 0, 0, 0.6);
    justify-content: center;
    position: absolute;
    top: 0;
    left: 0;
    bottom: 0;
    right: 0;
    z-index: 100;
  }
  .modal {
    background-color: white;
    border-radius: 1rem;
    padding: 0.5rem 1rem 1.5rem 1rem;
  }
  label, p {
    font-weight: lighter;
  }
  label {
    font-size: 12px;
    position: relative;
    background-color: white;
    margin-left: -2.5rem;
    padding-left: 0.3rem;
    padding-right: 0.3rem;
  }
  input {
    text-align: left;
    border: 1px solid black;
    border-radius: 0.5rem;
    padding: 0.7rem 0.5rem 0.7rem 0.5rem;
    margin-top: -9px;
  }
  .date {
    margin-top: -0.5rem;
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
  }
  .date > .info > label {
    margin-left: -5.1rem;
  }
  .btns {
    display: flex;
    justify-content: space-evenly;
  }
  button, slot {
    margin-top: 1rem;
    background-color: #FFBE12;
    border-radius: 1rem;
    border: none;
    padding: 0.5rem;
    width: 8rem;
    box-shadow: 1px 1px 1px 1px grey;
    cursor: pointer;
  }

</style>
