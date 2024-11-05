<template>
    <div class="pages-waitlist min-h-screen flex flex-col items-center justify-center">

        <FeaturesWaitlistBoxContainer>
        <div>
           <ContentList path="/news">
                <template #default="{ list }">
                    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
                        <NuxtLink 
                            v-for="article in list" 
                            :key="article._path"
                            :to="article._path"
                            class="bg-white/10 rounded-lg p-6 hover:bg-white/20 transition-colors cursor-pointer"
                        >
                            <h2 class="text-xl font-bold text-white mb-2">{{ article.title }}</h2>
                            <p v-if="article.description" class="text-white/70">{{ article.description }}</p>
                            <div class="mt-4 text-sm text-white/50">
                                <span v-if="article.date">{{ new Date(article.date).toLocaleDateString() }}</span>
                            </div>
                        </NuxtLink>
                    </div>
                </template>
                <template #not-found>
                    <p class="text-white/70 text-center">No articles found.</p>
                </template>
            </ContentList>
        </div>
        </FeaturesWaitlistBoxContainer>

    </div>        
</template>
<script setup>

</script>

<style>
    .pages-waitlist {
    min-height: calc(100vh - 100px);
}
</style>
