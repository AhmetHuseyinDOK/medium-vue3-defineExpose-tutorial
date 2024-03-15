<template>
    <div>
        <div ref="animatedElement" class="animate-box">Animate Me</div>
        <button @click="triggerAnimation">Trigger Animation</button>
    </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const animatedElement = ref<HTMLElement | null>(null);

const triggerAnimation = () => {
    if (animatedElement.value) {
        animatedElement.value.style.transition = 'transform 0.5s ease';
        animatedElement.value.style.transform = 'scale(1.5)';
        setTimeout(() => {
            if (animatedElement.value) {
                animatedElement.value.style.transform = 'scale(1)';
            }
        }, 500);
    }
};

defineExpose({
    triggerAnimation
})

</script>

<style>
.animate-box {
    width: 100px;
    height: 100px;
    background-color: skyblue;
    margin: 20px;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: transform 0.5s ease;
}
</style>