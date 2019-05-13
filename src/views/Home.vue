<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <TwoLists msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import TwoLists from "../components/HelloWorld";

export default {
  name: 'home',
  components: {
    TwoLists,
    HelloWorld
  }
}
</script>
