<template>
    <div>
        <h2 class="title"> Comp Axios</h2>
        <tablerG :options="{editable: true, deletable: true}" :dataList="[
        { name: 'a', astro: 'astA' },
        { name: 'b', astro: 'astB' },
        { name: 'c', astro: 'astC' }]
        ">
        </tablerG>
    </div>
</template>
<script>
import tablerG from "@/components/tablerG.vue"
// import axios from "axios"
export default {
    components: {
        tablerG
    },
    data(){
        return{
            dataList: null
        }
    }    
}
</script>
