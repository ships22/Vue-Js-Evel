<template>
    <div id="square" @click="isBlack = !isBlack" 
        :style="{'background': isBlack ? 'black' : 'purple'}">
        {{ users }}
    </div>
</template>
<script>
export default {
    props: ["users"],
    data() {
        return {
            isBlack: false
        }
    }
}
</script>
<style>
#square {
    height: 220px;
    width: 220px;
    margin: auto;
}
</style>