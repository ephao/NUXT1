  <template>
    <div class="pages-news min-h-screen flex flex-col items-center justify-center">
        <FeaturesWaitlistLabelMini />
        <FeaturesWaitlistBoxContainer class="w-2/3">
            <FeaturesWaitlistBoxHeader />
            <!-- <FeaturesWaitlistBoxDescription /> -->
            <ContentDoc class="text-white/70 mb-6"/>
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
    layout: 'waitlist'
})
</script>


