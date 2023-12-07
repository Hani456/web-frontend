<template>
    <div class="container">
        <div v-for="medicine of medicinesData" :key="medicine.medicine_id">
            <SingleMedicine :medicine=medicine />
        </div>
    </div>
</template>

<script>
    import SingleMedicine from "./SingleMedicine.vue";

    export default{
        name:"MedicinesList",
        components:{
            SingleMedicine
        },
        props:{
            medicinesData: Array
        }
    }
</script>

<style scoped>
    .container{
        display: grid;
        grid-template-columns:auto auto auto;
        grid-gap: 10px;
    }
</style>