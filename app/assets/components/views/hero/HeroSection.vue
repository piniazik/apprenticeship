<template>
    <div
        style="height: 800px; position: relative; overflow: hidden; background-color: #060010;"
    >
        <LaserFlow
            :horizontalBeamOffset="0.1"
            :verticalBeamOffset="0.0"
            color="#674ebc"
        />

        <TheHeader/>

        <div
            style="
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translateX(-50%);
        width: 70%;
        height: 54.5%;
        background-color: #060010;
        background-image: url('/img/product.png');
        background-repeat: no-repeat;
        background-position: center;
        background-size: cover;
        border-radius: 20px;
        border: 2px solid #674ebc;
        display: flex;
        align-items: center;
        justify-content: center;
        color: white;
        font-size: 2rem;
      "
        >
        </div>
    </div>
</template>

<script setup>
import LaserFlow from "@/assets/components/views/hero/LaserFlow.vue"
import TheHeader from "@/assets/components/header/TheHeader.vue"
</script>