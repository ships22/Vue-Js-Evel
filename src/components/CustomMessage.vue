<template>
    <div v-if="msg" id="cus_msg" :class="css">
        <p>
            {{msg}}...
        </p>
    </div>
</template>
<script>
export default {
    created(){
        this.$ebus.$on("notify", payload => {
            console.log("payload@CusMsg", payload.msg, payload.css);
            this.msg = payload.msg;
            this.css = payload.css;
        })
    }, 
    data() {
        return  {
            css: "is-default",
            msg: ""
        }
    }
}
</script>
<style scopped>
    
    .is-default {
        color: blue;
    }
    .success {
        border: 5px solid  green;
        color: green;
        
        background: rgb(236, 228, 228);
        font-weight: bold;
        transition: .5s;
        padding: 10px;
        font-size: 20px;
    }
    .warning {
        border: 5px solid  rgb(236, 56, 11);
        color: rgb(236, 56, 11);
        padding: 10px;
        background: rgb(236, 228, 228);
        font-weight: bold;
        transition: .5s;
        font-size: 20px;
    }
</style>


