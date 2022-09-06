<template>
    <div class="w-10/12 pt-10">
        <section class="flex flex-wrap w-11/12 m-auto bg-white p-4">
            <article v-for="article in articles" class="m-4 border-2 p-2">
                <h3>{{article.title}}</h3>
            </article>
        </section>
    </div>

</template>


<script lang="ts">
    import { defineComponent } from 'vue';
    export default defineComponent({
      name: 'MonthlyGrid',
      
    });
</script>

<script setup lang="ts">
    import { onMounted, ref } from 'vue';
    // type Article = object
    interface Article {
        title: string,

    }
    const articles = ref<[Article]>()


    onMounted(() => {
        fetch(`https://api.nytimes.com/svc/news/v3/content/all/all.json?api-key=eQhXe2kNTCVKkFf47qUCjFhmG5nSVB5O`).then(res => res.json()).then(data => {
            console.log(data)
            articles.value = data.results
        })
    })

</script>