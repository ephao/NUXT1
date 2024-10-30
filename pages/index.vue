<template>
    <div class="w-full flex flex-col items-center justify-center min-h-screen bg-[url('/bg2.jpg')] bg-cover bg-fixed">   

        <div class="mb-12">
            <h1 class="text-6xl font-bold text-white/70 animate-[pulse_3s_ease-in-out_infinite]">Coming soon!</h1>
        </div>
        <div class="p-8 rounded-xl backdrop-blur-sm bg-white/10 border border-white/20 text-center mb-12 shadow-[0_0_25px_rgba(255,255,255,0.15)] hover:shadow-[0_0_30px_rgba(255,255,255,0.25)] transition-shadow">
            <h2 class="text-4xl font-bold mb-4 text-white/70 font-serif">Cow AI</h2>
            <p class="text-white/70 mb-6">A New Tool for Livestock Farming</p>
            <UButton 
                to="https://forms.office.com/Pages/ResponsePage.aspx?id=DQSIkWdsW0yxEjajBLZtrQAAAAAAAAAAAAMAAGTtiixURTE1TUpONzlUTkhDUFI4NEEzSFhZQU9HNi4u" 
                target="_blank" 
                variant="outline" 
                class="px-8 text-white hover:bg-white/30"
            >Join Waitlist Now</UButton>
        </div>
        <div class="flex gap-6">
            <a 
                title="Follow X" 
                href="https://x.com"
                target="_blank"
                class="text-white/70 hover:text-white/90"
            >
                <Icon name="simple-icons:x" class="w-6 h-6" />
            </a>
            <a 
                title="Search in Google" 
                href="https://google.com"
                target="_blank"
                class="text-white/70 hover:text-white/90"
            >
                <Icon name="simple-icons:google" class="w-6 h-6" />
            </a>
        </div>  
    </div>        
</template>
<script setup>

</script>