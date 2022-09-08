<template>
    <div class="w-2/12 bg-white px-4">
        <h2 class="font-bold text-3xl p-3 font-['Abril_Fatface']">Sections</h2>
        <div class="flex flex-col items-start py-2">
            <Tag v-for="section in sections" :display_name="section.display_name" :section="section.section"/>
        </div>
    </div>
</template>

<script lang="ts">
    import { defineComponent } from 'vue';
    export default defineComponent({
      name: 'TagsBar',
    });
</script>
<script setup lang="ts">
    import { onMounted, ref } from 'vue';
    import Tag from './Tag.vue';

    interface Section {
        section: string,
        display_name: string

    }
    const sections = ref<[Section]>()


    onMounted(() => {
        fetch(`https://api.nytimes.com/svc/news/v3/content/section-list.json/get?api-key=eQhXe2kNTCVKkFf47qUCjFhmG5nSVB5O`).then(res => res.json()).then(data => {
            console.log(data)
            sections.value = data.results
        })
    })
</script>