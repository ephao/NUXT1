<template>
    <div class="w-full flex flex-col items-center justify-center min-h-screen bg-[url('/bg.jpg')] bg-cover bg-fixed ">   
        <div><span>waitlist</span></div>
        <div><h1>coming soon</h1></div>
        <div>
            <h2 class="text-4xl font-bold mb-4">Cow AI</h2>
            <p class="text-gray-500 mb-6">A new tool for Livestock Farming</p>
            <UButton 
                to="https://google.com" 
                target="_blank" 
                variant="outline"
                class="px-8 hover:bg-gray-100"
            >Subscribe Now</UButton>
        </div>
        <div>
            <a title="Follow X" href="https://x.com" >X </a>
            <a title="Search in Google" href="https://google.com" >Google </a>
        </div>  
    </div>        
</template>
<script setup>

</script>