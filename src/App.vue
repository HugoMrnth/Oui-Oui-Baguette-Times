<template>
  <header-view />
  <router-view/>
</template>

<style>
 * {
  font-family: Helvetica, sans-serif;
  padding: 0;
  margin: 0%;
  box-sizing: border-box;
 }
</style>


<script lang="ts">
  import { defineComponent } from 'vue';
  import HeaderView from './views/HeaderView.vue';
  export default defineComponent({
    name: 'App',
    components: {
    HeaderView
},
  });
  </script>
