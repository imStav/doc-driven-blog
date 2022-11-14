<script setup>
const { data } = await useAsyncData(() => {
    return queryContent('/blog/').find()
})
</script>

<template>
    <div>
        <div v-for="post in data" :key="post._id" class="border-l border-black dark:border-white pl-6 pb-4">
            <h2>{{ post.title }}</h2>
            <p>{{ post.description }}</p>
            <NuxtLink :to="post._path" class="no-underline px-4 py-2 bg-black prose-invert dark:bg-white dark:prose rounded-md">
                Read more
            </NuxtLink>
        </div>
    </div>
</template>