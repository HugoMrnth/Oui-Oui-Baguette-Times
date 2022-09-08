<template>
    <div class="w-8/12 m-auto pt-5">
        <p class="text-2xl font-['Abril_Fatface']">Votre recherche : {{route.params.query}}</p>
        <section class="mt-10 mx-auto bg-white pt-10 grid grid-cols-3">
                <ArticleCard v-for="article in col1" :title="article.headline.main" :kicker="article.headline.kicker" :image="article.multimedia != null ? article.multimedia[2].url : null" :abstract="article.abstract" :url="article.url" />
        </section>
    </div>
</template>
<script lang="ts">
    import { defineComponent } from 'vue';
    import ArticleCard from '@/components/ArticleCard.vue';
    export default defineComponent({
      name: 'SearchView',
      components: {
        ArticleCard
    },
    });
    </script>
    
    <script setup lang="ts">
    import { ref, onMounted, provide, watch } from 'vue';
    import { useRoute } from 'vue-router'
    const route = useRoute()
    
    interface Article {
        title: string,
        abstract: string,
        byline: string,
        published_date: string,
        multimedia: Array<{url:string}>,
        url: string,
        section: string,
        kicker: string

    }
    const col1 = ref<[Article]>()
    const col2 = ref<[Article]>()
    const col3 = ref<[Article]>()
    watch(route, () => {
        console.log('change has been made')
        fetchSearch()
    })

    onMounted(() => {
        fetchSearch()
    })
    function fetchSearch(): void {
        fetch(`https://api.nytimes.com/svc/search/v2/articlesearch.json?q=${route.params.query}&api-key=eQhXe2kNTCVKkFf47qUCjFhmG5nSVB5O`).then(res => res.json()).then(data => {
            console.log(data)
            col1.value = data.response.docs
           
        })
    }
    </script>