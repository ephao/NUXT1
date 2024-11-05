<template>
    <div class="fixed top-0 left-1/2 -translate-x-1/2 z-50 backdrop-blur-sm bg-black/10 rounded-full px-6 mt-4">
        <nav class="flex items-center justify-between h-16">
            <NuxtLink to="/" class="text-white/70 font-bold text-xl mr-8">Cow AI</NuxtLink>
            <div class="flex items-center gap-4">
                <UButton 
                    variant="ghost" 
                    to="/waitlist" 
                    class="text-white/70 hover:text-white"
                >
                    Waitlist
                </UButton>
                <UButton 
                    variant="ghost"
                    to="/about"
                    class="text-white/70 hover:text-white" 
                >
                    About
                </UButton>
                <UButton 
                    variant="ghost"
                    to="/news"
                    class="text-white/70 hover:text-white" 
                >
                    News
                </UButton>
            </div>
        </nav>
    </div>
</template>

<style>
    .common-navbar {
        height: 40px;
    }
</style>