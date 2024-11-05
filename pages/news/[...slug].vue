  <template>
    <div class="pages-news min-h-screen flex flex-col items-center justify-center">
        <FeaturesWaitlistLabelMini />
        <FeaturesWaitlistBoxContainer class="w-2/3">
            <FeaturesWaitlistBoxHeader />
            <!-- <FeaturesWaitlistBoxDescription /> -->
            <ContentDoc class="text-white/70 mb-6"/>
            <FeaturesWaitlistBoxJoinButton />
        </FeaturesWaitlistBoxContainer>

    </div>        
</template>
<script setup>
definePageMeta({
    layout: 'waitlist'
})
</script>


