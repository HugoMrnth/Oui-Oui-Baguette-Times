<template>
    <div class="flex py-6 px-4 w-full justify-center items-end border-b-2 border-zinc-300">
        <form class="flex flex-1">   
            <label for="default-search" class="mb-2 text-sm font-medium text-gray-900 sr-only dark:text-gray-300">Search</label>
            <div class="relative">
                <div class="flex absolute inset-y-0 left-0 items-center pl-3 pointer-events-none">
                    <svg aria-hidden="true" class="w-5 h-5 text-gray-500 dark:text-gray-400" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"></path></svg>
                </div>
                <input type="search" id="default-search" class="block p-2 pl-10 w-full text-sm text-gray-900 bg-gray-50 rounded-lg border border-gray-300 focus:ring-blue-500 focus:border-blue-500 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500" placeholder="Search articles" required>
            </div>
        </form>
        <h1 class="font-['Abril_Fatface'] text-4xl flex-1">The Oui Oui Baguette Times<i class="fa fa-umbrella" aria-hidden="true"></i></h1>
        <nav class="flex-1 text-right">
            <p><i class="fa fa-bars text-2xl" aria-hidden="true"></i></p>
        </nav>
    </div>

</template>


<script lang="ts">
    import { defineComponent } from 'vue';
    
    export default defineComponent({
      name: 'HeaderView',
      
    });
</script>

<style scoped>
    .box{
        box-shadow: 5px 15px 5px red;
    }
</style>