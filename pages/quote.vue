<template>
   <div class="pages-waitlist min-h-screen flex flex-col items-center justify-center">
        <FeaturesWaitlistBoxContainer class="w-2/3 mt-20">
             <div class="text-white/70 mb-6 prose prose-invert max-w-none" v-if="randomArticle">
                <h1 class="text-3xl font-bold mb-4">{{ randomArticle.title }}</h1>

                <ContentRendererMarkdown :value="randomArticle" />
            </div>


        </FeaturesWaitlistBoxContainer>

    </div>        
</template> 
<script setup>
useHead({
    title:'Quote'
    })
definePageMeta({
    layout: 'quote',

})

// 创建一个响应式引用变量randomArticle并初始化为null
const randomArticle = ref(null);    

// 获取'quote'内容集合中的文档总数
const count = await queryContent('quote').count();

// 生成一个0到count-1之间的随机索引
const randomIndex = Math.floor(Math.random() * count);

// 从'quote'内容集合中查询一条记录
// limit(1)限制返回1条记录
// skip(randomIndex)跳过randomIndex条记录
// find()执行查询
const articles = await queryContent('quote')
    .limit(1)
    .skip(randomIndex)
    .find();

// 将查询到的第一条记录赋值给randomArticle
randomArticle.value = articles[0];  

</script>

<style>
    .pages-waitlist {
    min-height: calc(100vh - 100px);
}
</style>
