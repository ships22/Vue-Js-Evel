<template>
  <div id="app">
    <CustomMessage/>
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link> | 
      <router-link to="/users">User</router-link> | 
      <router-link to="/parent-enfant">Parent/Enfant</router-link> |
      <router-link to="/DataTabler">Data Table</router-link> |
      <router-link to="/TablerWithGuillaume">DataTableWith Guillaume</router-link> |
      <router-link to="/T-shirts">T-shirts Box</router-link>
    </div>
    <router-view/>
    <footer></footer>
  </div>
</template>
<script>
import CustomMessage from "@/components/CustomMessage.vue";

export default {
  components: {
    CustomMessage
  }
}
</script>

<style lang="scss">
#app {
  color: #2c3e50;
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  padding: 20px;
}
#nav {
  padding: 20px 20px 20px 0;
  a {
    color: #2c3e50;
    font-weight: bold;
    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
.warning-box {
  background-color: #fff3cd;
  border: 1px solid;
  border-color: #ffeeba;
  border-radius: 0.3rem;
  color: #856404;
  padding: 6px;
}
</style>