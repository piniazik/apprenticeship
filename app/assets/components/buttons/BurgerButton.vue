<template>
    <PrimaryButton
        customClass="flex-col p-2 h-10 w-10"
        @onClick="openMenu"
    >
        <div
            class="bg-white-100 block rounded-full transition-all duration-300 ease-out h-0.5 w-6"
            :class="!isOpen ? 'relative rotate-135 top-0 mb-0' : 'mb-1'"
        >
        </div>
        <div
            class="bg-white-100 block transition-all duration-300 ease-out h-0.5 w-6"
            :class="!isOpen ? 'opacity-0 mb-0' : 'opacity-100 mb-1'"
        >
        </div>
        <div
            class="bg-white-100 block transition-all duration-300 ease-out h-0.5 w-6"
            :class="!isOpen ? 'relative -rotate-135 bottom-1' : ''"
        >
        </div>
    </PrimaryButton>
</template>
<script setup>
import PrimaryButton from "@/assets/components/buttons/PrimaryButton.vue"

const props = defineProps({
    isOpen: {
        type: Boolean,
        default: false
    }
})

const emits = defineEmits(['update:isOpen'])

function openMenu() {
    if (process.client) {
        if (props.isOpen) {
            document.body.classList.add('overflow-hidden')
        } else {
            document.body.classList.remove('overflow-hidden')
        }
        emits('update:isOpen', !props.isOpen)
    }
}
</script>