<template>
   <div class="pages-waitlist min-h-screen flex flex-col items-center justify-center">
        <FeaturesWaitlistBoxContainer class="w-2/3 mt-20">
             <div class="text-white/70 mb-6 prose prose-invert max-w-none" v-if="randomArticle">
                <!-- ContentRenderer是通用渲染器,可以渲染任何类型的内容,包括Markdown、Vue组件等 -->
                <!-- 而ContentRendererMarkdown专门用于渲染Markdown内容 -->
                <!-- 这里我们只需要使用ContentRenderer即可,因为它能够自动识别并正确渲染Markdown内容 -->
                <ContentRenderer :value="randomArticle" />
                
                <!-- 显示随机文章的标题,使用text-3xl(大字号)、加粗(font-bold)和下边距(mb-4)样式 -->
                <h1 class="text-3xl font-bold mb-4">{{ randomArticle.title }}</h1>
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
