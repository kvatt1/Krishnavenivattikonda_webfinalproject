<template>
   
    <li v-for="item in items" :key="item.id">{{ item.name }}</li>
    
    <div v-for="medicine of medicines" :key="medicine._id" >
     
       <SingleMedicine :medicine=medicine />

    </div>
</template>

<script>
import SingleMedicine from './SingleMedicine.vue'

export default {
    name: 'MedicineBox',
    props:{
        medicines: Object
    },
    components:{
        SingleMedicine
    }
    
}
</script>

<style scoped>

</style>
