<template>
  <div class="container">
    <table>
      <tr>
        <th>Título</th>
        <th>Fecha de Creación</th>
        <th>Acción</th>
      </tr>
      <tr v-for="(report, index) in reports"
        :key="index">
        <td>
          {{report.fileName}}
        </td>
        <td class="date">
          {{report.date}}
        </td>
        <td class="downloadBtn">
          Descargar
        </td>
      </tr>
    </table>
  </div>
</template>

<script>

  export default {
    name: 'ReportsRecord',
    props: {
      /* reports: Array, */
      nuevoReporte: Object,
    },
    data() {
      return{
        reports: [
          {
            fileName: "Reporte de Usuario 1",
            date: "13/05/2022"
          },
          {
            fileName: "Reporte de Usuario 2",
            date: "14/05/2022"
          },
          {
            fileName: "Reporte de Usuario 3",
            date: "15/05/2022"
          }
        ],
      }
    },
    created: function(){
      let dataDB = JSON.parse(localStorage.getItem('newReports'));
      console.log(dataDB);
      if(dataDB != null){
        console.log('hay nuevos reportes');
        this.reports.push(dataDB);
      }
    }
  };

</script>

<style scoped>

  .container {
    margin: 0;
    padding: 0.5rem;
    width: 80%;
  }
  table {
    width: 70%;
    margin: 1rem;
    padding: 10px 30px 15px 30px;
    gap: 10px;
    background: #4563E6;
    border-radius: 10px;
  }
  th, td {
    color: white;
    padding-bottom: 0.5rem;
  }
  th > th {
    font-size: 0.8rem;
  }
  tr > td {
    border-top: 1px solid;
    padding-top: 0.5rem;
    font-size: 0.7rem;
  }
  .date {
    border-left: 1px solid;
    border-right: 1px solid;
  }
  .downloadBtn {
    cursor: pointer;
  }

</style>
