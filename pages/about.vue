<template>
   <div class="pages-waitlist min-h-screen flex flex-col items-center justify-center">
        <FeaturesWaitlistLabelMini />
        <FeaturesWaitlistBoxContainer>
            <ContentDoc class="text-white/70 mb-6"/>
            <UButton 
            to="/" 
            target="_blank" 
            variant="outline" 
                class="px-8 text-white mt-4 hover:bg-white/30"
            >Back to Cow AI</UButton>
        </FeaturesWaitlistBoxContainer>

    </div>        
</template> 
<script setup>
useHead({
    title:'About'
    })
</script>

<style>
    .pages-waitlist {
    min-height: calc(100vh - 100px);
}
</style>
