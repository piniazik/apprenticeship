<template>
    <div class="flex flex-col min-h-screen">
        <TheHeader
            :key="route.path"
        />
        <main class="flex-1 relative">
            <slot />
        </main>
    </div>
</template>
<script setup>
import TheHeader from "@/assets/components/header/TheHeader.vue"

const route = useRoute()

</script>