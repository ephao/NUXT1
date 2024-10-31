<template>
    <div class="pages-waitlist min-h-screen flex flex-col items-center justify-center">
        <FeaturesWaitlistLabelMini />
        <FeaturesWaitlistBoxContainer>
            <FeaturesWaitlistBoxHeader />
            <FeaturesWaitlistBoxDescription />
            <FeaturesWaitlistBoxJoinButton />
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
