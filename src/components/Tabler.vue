<template>

    <table id="tabler">
        <tr>
            <th v-for="(th , id) in head" :key="id">
                {{ th }}
            </th>
        </tr>
        
        <tr v-if="openDataParis" v-for="(data, id) in openDataParis" :key="id">
            <td>{{ id + 1}}</td>
            <td>
                {{ data.fields.nom_du_cafe }}
            </td>
            <td>
                {{ data.fields.adresse }}
            </td>
            
        </tr>
       
    </table>
            
    
</template>
<script>

export default {
    
    props: ["openDataParis"],
    
    data(){
        return {
            head: ["No", "Name", "Address"],
            body: ""
            
        }
      
    }
    
    
}
</script>
<style scoped>
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
    border: 3px solid rgb(8, 126, 4);
    height: 50px;
    font-size: 22px;
    font-weight: bold;
}
td {
    text-align: center;
    border: 3px solid rgb(44, 182, 10);
    height: 40px;
    font-size: 18px;
}

</style>
       
       
         
        
         
             

    
   
    
           
        
          
