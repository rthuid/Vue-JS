<template>
  <div>
    <mainHeader />
    <div class="outer">
      <h1>Welcome to Your Vue.js App</h1>
      <img src="../assets/main.png" alt="logo">
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import mainHeader from '@/components/header.vue'

export default {
  name: 'home',
  components: {
    mainHeader
  }
}
</script>
