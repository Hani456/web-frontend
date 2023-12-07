<template>
    <div class="card">
        <div class="medicine-img">
           <img :src=medicine?.medicine_img alt="medicine" />
        </div>
        <div class="medicine-data">
            <h3>{{medicine?.medicine_name}}</h3>
            <h4>${{medicine?.medicine_price}}</h4>
            <div class="weight">
                <img src="https://cdn.icon-icons.com/icons2/2248/PNG/512/weight_icon_135019.png" alt="weight image"/>
                <div :style="{'margin-right':'40px'}">
                    {{medicine?.medicine_weight}}
                </div> 
                <span>
                    <img src="https://www.kindpng.com/picc/m/157-1575433_medicine-medicine-icon-icon-hd-png-download.png" alt="quantity image"/>
                    {{medicine?.medicine_quantity}} pieces
                </span>
            </div>
            <br/>
            <span v-if="!readMoreActivated">{{medicine?.medicine_description.slice(0,20)}}</span>
            <a v-if="!readMoreActivated" @click="activateReadMore" href="#">
                ... Read More
            </a>
            <span v-if="readMoreActivated"> {{medicine?.medicine_description}} </span>
            <a  v-if="readMoreActivated" @click="activateLessMore" href="#">
                ... Less More
            </a>
            <p> Expiry : {{medicine?.medicine_exp_date}} </p>
        </div>
    </div>
</template>

<script>
    export default{
        name:"SingleMedicine",
        props:{
            medicine: Object
        },
        data(){
            return{
                readMoreActivated: false
            }
        },
        methods: {
            activateReadMore(){
                this.readMoreActivated = true;
            },
            activateLessMore(){
                this.readMoreActivated = false;
            },
        }
    }
</script>

<style scoped>
    .card{
        display:flex;
        justify-content: space-evenly;
        align-items: center;
        border:transparent;
        border-radius: 4px;
        padding: 10px;
        box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
    }
    .medicine-img img{
       width: 200px;
       height: 200px;
    }
    a:link, 
    a:visited,
    a:active,
    a:hover{
        text-decoration: none;
        color: #00000;
    }
    .weight img{
        width: 30px;
        height: 30px;
    }
    .weight{
        display:flex;
        align-items: center;
    }
</style>

