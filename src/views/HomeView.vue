<template>
  <div class=" bg-gray-100 flex">
      <PopularSideBarVue />
      <MonthlyGrid />
      <TagsBar />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
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

<script setup lang="ts">
import { ref, onMounted, provide } from 'vue';

const selSection = ref<String>('all')
provide("selSection", selSection)

</script>