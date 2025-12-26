<template>
    <header>
    <div class="top-[2em] left-0 z-1 absolute w-full h-15">
        <div
            class="flex justify-between items-center bg-[rgba(255,255,255,0.05)] backdrop-filter backdrop-blur-[10px] mx-auto my-0 px-6 py-4 border border-[rgba(255,255,255,0.2)] rounded-[50px] w-[90%] md:w-[60%] h-full"
            style="backdrop-filter: blur(10px); box-shadow: rgba(0, 0, 0, 0.1) 0px 4px 30px;"
        >
            <NuxtLink to="/">
                <LogoIcon class="w-20 h-20"/>
            </NuxtLink>
            <div class="xl:hidden flex items-center">
                <BurgerButton v-model:isOpen="showHeaderMobileMenu"/>
            </div>
            <div
                class="items-center gap-6 font-semibold max-xl:items-start"
                :class="!showHeaderMobileMenu ? 'max-xl:flex! mobile-menu' : 'max-xl:hidden'"
            >
                <nav class="">
                    <ul class="flex items-center justify-center gap-8 max-xl:flex-col max-xl:gap-0 max-xl:items-start">
                        <li
                            v-for="(link, index) in links"
                            :key="index"
                            class="flex max-xl:mb-4 max-xl:last-of-type:mb-0"
                        >
                            <NuxtLink
                                class="text-white-100 text-sm transition-all duration-300 cursor-pointer hover:text-purple-600"
                                :to="link.href"
                                style="box-shadow: rgba(0, 0, 0, 0.1) 0px 4px 30px;"
                            >
                                {{ link.name }}
                            </NuxtLink>
                        </li>
                    </ul>
                </nav>
            </div>
        </div>
    </div>
    </header>
</template>
<script setup>
import LogoIcon from "@/assets/icons/LogoIcon.vue"
import BurgerButton from "@/assets/components/buttons/BurgerButton.vue"

const showHeaderMobileMenu = ref(true)
const route = useRoute()

const links = [
     {
         name: 'Pricing',
         href: '/pricing'
     },
     {
         name: 'About',
         href: '/about'
     },
     {
         name: 'Contact',
         href: '/contact'
     },
 ]

watch(() => route.fullPath, () => {
    if (process.client) {
        document.body.classList.remove('overflow-hidden')
        showHeaderMobileMenu.value = true
    }
}, { immediate: true })
</script>