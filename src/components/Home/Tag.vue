<template>
    <button class=" font-[Open_Sans] hover:bg-gray-200 rounded hover:scale-125 p-1 m-1 text-xs" @click="changeSection(section)">{{display_name}}</button>
</template>


<script lang="ts">
    import { defineComponent } from 'vue';
    export default defineComponent({
      name: 'Tag',
      props: {
        section: String,
        display_name: String
      }
    });
</script>


<script setup lang="ts">
    import { inject } from 'vue';
    const selSection = inject('selSection')

    function changeSection(section : string) : void {
        selSection.value = section
    }

</script>