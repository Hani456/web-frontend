<template>
    <header>
        <h1>DRUGSTORE</h1>
        <img src="https://img.freepik.com/premium-vector/tiny-pharmacist-with-aid-pills-tablet-vector-pharmacist-with-drug-tablet-pharmaceutical-pill-aid-illustration-medicine-medicare_102902-5963.jpg?w=1060" alt="medicine image"/>
    </header>
</template>

<script>
    export default{
        name:"MedicineHeader",
    }
</script>

<style scoped>
    header{
        display: flex;
        justify-content: space-evenly;
        align-items: center;
        color: #70bffe;
    }
    img{
        width: 30%;
        height: 30%;
    }
</style>