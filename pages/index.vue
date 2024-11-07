<template>
    <div class="pages-waitlist min-h-screen flex flex-col items-center justify-center">
        <FeaturesWaitlistLabelMini />
        <FeaturesWaitlistBoxContainer>
            <FeaturesWaitlistBoxHeader />
            <!-- <FeaturesWaitlistBoxDescription /> -->
            <ContentDoc class="text-white/70 mb-6"/>
            <FeaturesWaitlistBoxJoinButton />
        </FeaturesWaitlistBoxContainer>

    </div>        
</template>
<script setup>
useHead({
    title:'Cow AI'
    })
</script>

<style>
    .pages-waitlist {
    min-height: calc(100vh - 100px);
}
</style>
