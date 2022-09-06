<template>
    <div class="flex flex-col border-r-2 w-2/12 bg-white  border-zinc-300">
        <h3 class="text-2xl font-bold text-center mt-4 mb-6">Populars Articles</h3>
        <section class="flex flex-col px-4">
            <article v-for="article in articles" class="my-4 flex flex-col">
                <router-link to="/article">
                    <div class="flex text-xs">
                        <p class="mr-3 text-yellow-500">{{article.source}}</p>
                        <p>{{article.published_date}}</p>
                    </div>
                    <h4 class="font-bold text-sm my-1">{{article.title}}</h4>
                    <p class="italic text-xs my-1 text-right">{{article.byline}}</p>
                    <div class="mt-2 border-b-2 border-black w-3/12"></div>
                </router-link>
                </article>
        </section>
    </div>
</template>
<script lang="ts">
    import { defineComponent } from 'vue';
    
    export default defineComponent({
      name: 'PopularSideBar',
      
    });
</script>

<script setup lang="ts">
    import { onMounted, ref } from 'vue';
    // type Article = object
    interface Article {
        title: string,
        source: string,
        published_date: string,
        byline: string

    }
    const articles = ref<[Article]>()


    onMounted(() => {
        fetch('https://api.nytimes.com/svc/mostpopular/v2/viewed/1.json?api-key=eQhXe2kNTCVKkFf47qUCjFhmG5nSVB5O').then(res => res.json()).then(data => {
            // console.log(data)
            articles.value = data.results
        })
    })

</script>