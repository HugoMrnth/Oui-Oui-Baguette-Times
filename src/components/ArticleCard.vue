<template>
    <article class="m-1 p-4">
        <div class="flex flex-col font-bold text-lg">
            <h3><span class="text-yellow-500 mr-2" v-if="kicker != ''">{{kicker}} -</span>{{title}}</h3>
            <p class="text-xs font-normal my-2">{{abstract}}</p>
        </div>
        <img :src="image" alt="" v-if="image != null" class="">
    </article>
</template>


<script lang="ts">
    import { defineComponent } from 'vue';
    export default defineComponent({
      name: 'ArticleCard',
      props: {
        title: String,
        abstract: String,
        byline: String,
        published_date: String,
        image: String,
        uri : String,
        section: String,
        kicker: String
      }
    });
</script>