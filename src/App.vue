<template>
    <Header />
    <main class="mt-[90px] lg:mt-[189px]">
        <div class="py-20 container">
            Lorem ipsum, dolor sit amet consectetur adipisicing elit. Fuga quos,
            vitae laboriosam, cumque expedita id repellendus alias sequi neque
            nostrum ratione saepe illo voluptate dolores possimus? Et voluptas
            quam tempora?
        </div>
    </main>
    <Footer />
</template>

<script setup lang="ts">
import Header from './components/Header/Header.vue';
import Footer from './components/Footer/Footer.vue';
</script>

<style>
#app {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
}
</style>
