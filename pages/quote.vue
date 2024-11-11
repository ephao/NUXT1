<template>
   <div class="pages-waitlist min-h-screen flex flex-col items-center justify-center">
        <FeaturesWaitlistBoxContainer class="w-2/3 mt-20">
            <div v-if="randomArticle" class="animate-fade-in">
                <!-- Header Image -->
                <div class="relative w-full h-64 mb-6 overflow-hidden rounded-lg">
                    <img 
                        :src="randomArticle.img" 
                        :alt="randomArticle.title" 
                        class="absolute w-full h-full object-cover transition-transform duration-300 hover:scale-105 opacity-90 hover:opacity-100"
                    >
                    <div class="absolute bottom-0 left-0 right-0 p-6 bg-gradient-to-t from-black/80 to-transparent">
                        <h1 class="text-3xl font-bold text-white">{{ randomArticle.title }}</h1>
                    </div>
                </div>

                <div class="text-white/70 prose prose-invert max-w-none">
                    <ContentRenderer :value="randomArticle">
                        <ContentRendererMarkdown :value="randomArticle" />
                    </ContentRenderer>
                    <div class="flex justify-center mt-8">
                        <button 
                            @click="fetchRandomArticle"
                            class="px-6 py-2 bg-white/10 hover:bg-white/20 text-white rounded-lg transition-colors duration-200 flex items-center space-x-2"
                        >
                            <span>Refresh Quote</span>
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 4v5h.582m15.356 2A8.001 8.001 0 004.582 9m0 0H9m11 11v-5h-.581m0 0a8.003 8.003 0 01-15.357-2m15.357 2H15" />
                            </svg>
                        </button>
                    </div>
                </div>
            </div>

            <div v-else class="flex flex-col items-center justify-center py-20 space-y-4">
                <div class="w-16 h-16 border-4 border-white/20 border-t-white rounded-full animate-spin"></div>
                <p class="text-white/70 text-lg">Loading inspiring quotes...</p>
            </div>
        </FeaturesWaitlistBoxContainer>

    </div>        
</template> 
<script setup>
import { onMounted, ref } from 'vue'
useHead({
    title:'Quote'
    })
definePageMeta({
    layout: 'quote',
})

const randomArticle = ref(null)

// 在服务端获取随机文章
const fetchRandomArticle = async () => {
    // 获取'quote'内容集合中的文档总数
    const count = await queryContent('quote').count()

    // 生成一个0到count-1之间的随机索引
    const randomIndex = Math.floor(Math.random() * count)

    // 从'quote'内容集合中查询一条记录
    const articles = await queryContent('quote')
        .limit(1)
        .skip(randomIndex)
        .find()

    // 将查询到的第一条记录赋值给randomArticle
    randomArticle.value = articles[0]
}


// 当组件挂载完成时执行fetchRandomArticle函数
// onMounted是Vue3的生命周期钩子,会在组件挂载到DOM后自动执行
// 这里用它来确保在页面加载完成后自动获取并显示一篇随机文章
onMounted(fetchRandomArticle);  

</script>

<style>
    .pages-waitlist {
    min-height: calc(100vh - 100px);
}
</style>
