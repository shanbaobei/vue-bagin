<template>
  <div id="app">
      <ul>
      <li> <router-link to='/'>Home</router-link></li>
      <li> <router-link to='/order'>Order</router-link></li>
      <li> <router-link to='/aaa'>aaa</router-link></li>
    </ul>
    <router-view></router-view>
  </div>
</template>
<script>
export default {
}
</script>
<style lang="scss">
* {
  padding: 0;
  margin: 0;
}
.left {
  float: left;
  width: 40%;
}
.right {
  float: left;
}

</style>
