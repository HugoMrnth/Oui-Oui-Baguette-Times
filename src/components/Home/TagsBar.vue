<template>
    <div class="w-full bg-white px-4">
        <h2 class="font-bold text-3xl p-3">Sections</h2>
        <div class="flex flex-wrap">
            <button v-for="section in sections" class="border-2 rounded p-1 px-2 m-2 bg-gray-100 text-xs">{{section.display_name}}</button>
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