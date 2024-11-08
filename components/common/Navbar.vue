<template>
    <div class="fixed top-0 left-1/2 -translate-x-1/2 z-50 backdrop-blur-sm bg-black/50 rounded-full px-6 mt-4">
        <nav class="flex items-center justify-between h-16">
            <NuxtLink to="/" class="text-white font-bold text-xl mr-8">Cow AI</NuxtLink>
            <div class="flex items-center gap-4">
                <UButton 
                    variant="ghost" 
                    to="/waitlist" 
                    class="text-white hover:text-white"
                >
                    Waitlist
                </UButton>
                <UButton 
                    variant="ghost"
                    to="/about"
                    class="text-white hover:text-white" 
                >
                    About
                </UButton>
                <UButton 
                    variant="ghost"
                    to="/news"
                    class="text-white hover:text-white" 
                >
                    News
                </UButton>
                <UButton 
                    variant="ghost"
                    to="/quote"
                    class="text-white hover:text-white" 
                >
                    Quote
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