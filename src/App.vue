<template>
  <div id="app" class="">
   <Balance />
  
   <!-- <hr>
    <Support /> -->
  </div>
     
   
</template>

<script>
import Balance from './components/Balance.vue';




export default {
  name: 'App',
  components: {
    Balance,
    
   
}
}
</script>

<style lang="scss">
body{
  margin: 0 auto;
  padding: 0;
  box-sizing: border-box;
}

#app{
  display: flex;
  justify-content: center
}

</style>
