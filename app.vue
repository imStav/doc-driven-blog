<script setup>
const { navigation } = useContent()
</script>

<template>
    <div class="min-h-screen prose dark:prose-invert bg-slate-100 dark:bg-black">
        <div class="">
            <nav class="flex justify-center not-prose">
                <li 
                    v-for="link in navigation" :key="link._path"
                    class="list-none mx-4"
                >
                    <NuxtLink :to="link._path">
                        {{ link.title }}
                    </NuxtLink>
                </li>
            </nav>
        </div>

        <NuxtPage />
    </div>
</template>