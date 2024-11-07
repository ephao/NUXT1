<template>
   <div class="pages-waitlist min-h-screen flex flex-col items-center justify-center">
        <FeaturesWaitlistLabelMini />
        <FeaturesWaitlistBoxContainer>
            <p class="text-white"> Waitlist Page</p>
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
definePageMeta({
    layout: 'waitlist'
})
useHead({
    title:'Waitlist'
    })
</script>

<style>
    .pages-waitlist {
    min-height: calc(100vh - 100px);
}
</style>
