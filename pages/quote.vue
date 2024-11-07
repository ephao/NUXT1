<template>
   <div class="pages-waitlist min-h-screen flex flex-col items-center justify-center">
        <FeaturesWaitlistLabelMini />
        <FeaturesWaitlistBoxContainer>
             <div class="text-white/70 mb-6 " v-if="randomArticle">
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

const randomArticle = ref(null);    
// 获取文章总数
const count = await queryContent('quote').count();

  // 生成一个 0 到 count-1 的随机索引
const randomIndex = Math.floor(Math.random() * count);

  // 根据随机索引获取对应文章
const articles = await queryContent('quote')
    .limit(1)
    .skip(randomIndex)
    .find();

randomArticle.value = articles[0];  

</script>

<style>
    .pages-waitlist {
    min-height: calc(100vh - 100px);
}
</style>
