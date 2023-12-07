<template>
  <MedicineHeader/>
  <MedicinesList :medicinesData=medicinesList />
</template>

<script>
  import MedicinesList from "./components/MedicinesList.vue";
  import MedicineHeader from "./components/MedicineHeader.vue";

  export default{
    name:"App",
    components:{
      MedicinesList,
      MedicineHeader
    },
    data(){
      return{
        medicinesList:[]
      }
    },
    methods:{
      async displayMedicinesList(){
        const response = await fetch("https://medicine-data.onrender.com/api");
        const medicinesData = await response.json();
        console.log("medicinesData" , medicinesData);
        return medicinesData[0].medicines;
      }
    },
    async created(){
        this.medicinesList = await this.displayMedicinesList();
    }
  }
</script>

<style scoped>
</style>