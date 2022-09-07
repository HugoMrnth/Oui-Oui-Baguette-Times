<template>
    <div class="w-full">
        <section class="w-11/12 mt-10 mx-auto bg-white p-4 pt-10 grid grid-cols-3">
            <div class="flex flex-wrap">
                <ArticleCard v-for="article in col1" :title="article.title" :kicker="article.kicker" :image="article?.multimedia[2].url" :abstract="article.abstract"  />
            </div>
            <div class="flex flex-col">
                <ArticleCard v-for="article in col2" :title="article.title" :kicker="article.kicker" :image="article?.multimedia[2].url" :abstract="article.abstract"  />
            </div>
            <div class="flex flex-col">
                <ArticleCard v-for="article in col3" :title="article.title" :kicker="article.kicker" :image="article?.multimedia[2].url" :abstract="article.abstract"  />
            </div>
        </section>
    </div>

</template>


<script lang="ts">
    import { defineComponent } from 'vue';
    import ArticleCardVue from '../ArticleCard.vue';
    export default defineComponent({
      name: 'MonthlyGrid',
      components: ArticleCardVue
    });
</script>

<script setup lang="ts">
    import { onMounted, ref } from 'vue';
import ArticleCard from '../ArticleCard.vue';
    // type Article = object
    interface Article {
        title: string,
        abstract: string,
        byline: string,
        published_date: string,
        multimedia: Array<{url:string}>,
        uri : string,
        section: string,
        kicker: string

    }
    const col1 = ref<[Article]>()
    const col2 = ref<[Article]>()
    const col3 = ref<[Article]>()


    onMounted(() => {
        fetch(`https://api.nytimes.com/svc/news/v3/content/all/all.json?api-key=eQhXe2kNTCVKkFf47qUCjFhmG5nSVB5O`).then(res => res.json()).then(data => {
            // console.log(data)
            let temp = data.results
            col1.value = temp.slice(0,7)
            col2.value = temp.slice(7,14)
            col3.value = temp.slice(14)
        })
    })

</script>


<style scoped>
    
    article {
        height: fit-content;
        box-shadow: 10px 10px 30px rgba(0, 0, 0, 0.1);
    }
    
</style>