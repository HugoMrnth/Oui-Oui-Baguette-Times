<template>
  <div class="  bg-gray-100 flex">

    <PopularSideBarVue />
    <div class="w-10/12">
      <TagsBar />
      <MonthlyGrid />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import MostPopularVue from '@/components/Home/MostPopular.vue';
import PopularSideBarVue from '@/components/Home/PopularSideBar.vue';
import MonthlyGrid from '@/components/Home/MonthlyGrid.vue';
import TagsBar from '@/components/Home/TagsBar.vue';
export default defineComponent({
  name: 'HomeView',
  components: {
    PopularSideBarVue,
    MonthlyGrid,
    TagsBar
},
});
</script>
