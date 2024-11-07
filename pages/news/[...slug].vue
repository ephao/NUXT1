  <template>
    <div class="pages-news min-h-screen flex flex-col items-center justify-center">
        <FeaturesWaitlistBoxContainer class="w-2/3">

            <!-- <FeaturesWaitlistBoxDescription /> -->
            <ContentDoc class="text-white/70 mb-6 markdown-body text-left"/>
            <UButton 
                to="/news" 
                
                variant="outline" 
                class="px-8 text-white hover:bg-white/30"
            >Back to News
            </UButton>
        </FeaturesWaitlistBoxContainer>

    </div>        
</template>
<script setup>
definePageMeta({
    layout: 'news'
})
</script>

<style>
    .pages-news {
        min-height: calc(100vh - 100px);
    }
    .markdown-body {
        background-color: transparent;
    }
</style>

