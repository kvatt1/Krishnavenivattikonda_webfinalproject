<template>
    <div class="card">   
    <div>
        <h2>{{medicine.name}}</h2>    
        <div v-if="readMoreActivated">
        <p>{{medicine.category}}</p> 
        <p>Barcode : {{medicine.barcode}}</p>        
        <p>Weight : {{medicine.weight}}</p>
        <h4><p>Price : ${{medicine.price}}</p></h4>
        <p> Expiry : {{new Date(medicine.exp_date).getFullYear()}} </p>
        </div>

        <!-- Display the "Read More" link if readMoreActivated is false -->
        <a v-if="!readMoreActivated" @click="activateReadMore" href="#">... Read More</a>

        <!-- Display the "Less More" link if readMoreActivated is true -->
        <a v-if="readMoreActivated" @click="activateLessMore" href="#">... Less More</a>   
    </div>   

    <img :src="medicine.img" alt="medicine" />        
    </div>
   
</template>

<script>

export default{
    name: 'SingleMedicine',
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

.green{
    background-color: green;
}

h4{
    margin: 2px;
}

div{
    background-color: rgb(168, 246, 246);;
    color: blue;
    padding: 1em;
    text-align: center;
    width: 80%;
    margin: auto;
}

.red{
background-color: orangered !important;

}

img{
    width: 200px;
    height: 200px;
}

.card{
    display:flex;
    justify-content: space-evenly;
    align-items: center;
    border:transparent;
    border-radius: 4px;
    padding: 10px;
    box-shadow: 0 4px 8px 0 #acc7f6 , 0 6px 20px 0 #acc7f6;    
}

a:link, 
a:visited,
a:active,
a:hover{
    text-decoration: none;
    color: #00000;
}

</style>