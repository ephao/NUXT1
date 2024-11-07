<template>
     <div class="w-full min-h-screen bg-[url('/bg.jpg')] bg-cover bg-fixed">    
        <CommonNavbar /> 
        <div>
            <slot />
        </ div >
        <CommonSocialLinks />
        <CommonFooter />
    </div>
</template>