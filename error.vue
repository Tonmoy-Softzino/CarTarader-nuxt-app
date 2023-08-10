<script setup>
    const handleGoBack = () => {
        navigateTo("/");
    }
</script>

<template>
    <div class="flex items-center justify-center h-screen flex-col">
            <div class="customClass">404</div>
            <p class="mt-7 text-4xl">Page not found</p>
            <button @click="handleGoBack" class="rounded text-2xl mt-7 bg-slate-700 px-7 py-4">Go back home</button>
    </div>
</template>

<style scoped>
    .customClass{
        font-size: 3.5rem;
    }
    button{
        border-radius: .31rem;
        background-color: rgb(18, 18, 78);
        color: white;
        margin-top: 1rem;
        padding: .31rem .51rem
    }
</style>