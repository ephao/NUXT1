<template>
     <div class="w-full min-h-screen bg-[url('/bg2.jpg')] bg-cover bg-fixed">    
        <CommonNavbar /> 
        <div>
            <slot />
        </div>
        <CommonSocialLinks />
        <CommonFooter />
    </div>
</template>