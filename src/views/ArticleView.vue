<template>
    <h2>Article</h2>
    <p>{{route.params.id}}</p>
</template>
<script lang="ts">
    import { defineComponent } from 'vue';
    
    export default defineComponent({
      name: 'ArticleView',
      components: {
        
    },
    });
    </script>
    
    <script setup lang="ts">
    import { ref, onMounted, provide } from 'vue';
    import { useRoute } from 'vue-router'
    const route = useRoute()

    onMounted(() => {
        fetch(`https://api.nytimes.com/${route.params.id}`).then(res => res.json()).then(data => {
            console.log(data)
        })
    })
    
    </script>