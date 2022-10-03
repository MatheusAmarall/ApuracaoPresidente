<template>
  <div class="home">
  <img alt="Vue logo" src="../assets/urna.jpg" class="pic">
    <HelloWorld msg="Apuração eleições presidenciais"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'HomeView',
  components: {
    HelloWorld
  }
}
</script>

<style scoped>
  .pic {
    width: 300px;
    height: 200px;
  }
</style>
