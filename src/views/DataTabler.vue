<template>
<div>
    <h1> Data Table </h1>
    <Tabler :openDataParis="body"></Tabler>
    
</div>
    
</template>
<script>
import axios from 'axios';
import Tabler from "@/components/Tabler.vue";
export default {
    props: ['x'],

    components: {
        Tabler
    },
     data(){
       return {
        
        body : null,
        loading: true,
        errored: false
       }
    },
    mounted() {
        axios
        .get('https://opendata.paris.fr/api/records/1.0/search/?dataset=liste-des-cafes-a-un-euro&facet=arrondissement&refine.arrondissement=75015')
        .then(response => {
            console.log(response)
            this.body = response.data.records
            console.log(this.body);
        })
        .catch(error => {
            console.log(error)
            this.errored = true
        })
        .finally(() => this.loading = false)
    }
}
</script>
<style scoped>
    div {
        width: 100%;
        text-align: center;
    }
    
span {
    height: 50px;
    width: 100%;
    background: black;
    color: white;
    font-size: 18px;
    text-align: center;
    font-family: Helvetica, sans-serif;
}
table {
    width: 800px;
    margin: 0 auto;
     border-collapse: collapse;
}
th {
    border: 2px solid rgb(56, 54, 54);
}
td {
    text-align: center;
    border: 2px solid rgb(110, 107, 107);
   
}
</style>


