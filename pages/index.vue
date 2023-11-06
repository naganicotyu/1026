<template>
  <div class="mainPage">
  <headerTitle />
  <boxList />
  <footerInfo />
</div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'IndexPage',
})
</script>


<style>
.mainPage{
  background-color: rgb(38, 38, 214);
  min-height: 100vh;
}
</style>