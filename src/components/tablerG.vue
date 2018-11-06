<template>
     <table id="tabler">
         <thead class="head">
            <tr class="row">
            <th v-for="(data, key) in dataList[0]" :key="key">{{ key }}</th>
            <th v-if="options.editable"> Edit </th>
            <th v-if="options.deletable"> Delete </th>
            </tr>
        </thead>
        <tbody class="body">
            <tr class="row" v-for="(data, i) in dataList" :key="i">
                <td v-for="(val, prop) in data" :key="prop">
                    {{ val }}
                </td>
                <td v-if="options.editable" data-id="`data_${i}`">
                    <span> edit </span>
                </td>
                <td @click="deleteData(i)" v-if="options.deletable" data-id="`data_${i}`">
                    <span> X </span>
                </td>
            </tr>
        </tbody>
    </table>
</template>
<script>
export default {
    created() {
       
    },
    
    methods: {
    deleteData: function(index) {
        console.log('here');
    this.$ebus.$on("coming from tablerG", payload => {
            console.log("payload @ tablerG", payload);
        });
    
  }
    },
    props: ["dataList", "options"]
}
</script>
<style scopped>
#tabler, #tabler th, #tabler td {
    border: 1px solid;
    border-collapse: collapse;
}
#tabler th, #tabler td {
    padding: 10px;
    text-align: center;
}
.body .row:nth-child(odd) {
    background: silver;
}
</style>


       
