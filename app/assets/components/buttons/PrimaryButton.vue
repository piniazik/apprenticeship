<template>
    <button
        class="flex items-center justify-center text-xs font-semibold whitespace-nowrap rounded-4.5 transition-all"
        :class="customClass"
        @click="onClick"
    >
        <slot/>
    </button>
</template>

<script setup>
defineProps({
    customClass: {
        type: String,
        default: '',
    }
})

const emits = defineEmits(['onClick'])

function onClick() {
    emits('onClick')
}
</script>