<template>
  <div class="home bg-gray-100 flex">
    <PopularSideBarVue />
    <MonthlyGrid />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import MostPopularVue from '@/components/Home/MostPopular.vue';
import PopularSideBarVue from '@/components/Home/PopularSideBar.vue';
import MonthlyGrid from '@/components/Home/MonthlyGrid.vue';
export default defineComponent({
  name: 'HomeView',
  components: {
    PopularSideBarVue,
    MonthlyGrid
},
});
</script>
