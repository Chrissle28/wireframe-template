<template>
    <Header />
    <main class="mt-[90px] lg:mt-[189px]">
        <div class="container flex flex-wrap gap-5 py-20">
            <Button href="/test" primary> Lorem </Button>
            <Button secondary> Lorem </Button>
            <Button primary disabled> Lorem </Button>
            <Button secondary disabled> Lorem </Button>
            <Button primary square>
                <svg
                    xmlns="http://www.w3.org/2000/svg"
                    viewBox="-8 -5 24 24"
                    width="24"
                    fill="currentColor"
                >
                    <path
                        d="M5.314 7.071l-4.95-4.95A1 1 0 0 1 1.778.707l5.657 5.657a1 1 0 0 1 0 1.414l-5.657 5.657a1 1 0 0 1-1.414-1.414l4.95-4.95z"
                    ></path>
                </svg>
            </Button>
            <Button secondary square>
                <svg
                    xmlns="http://www.w3.org/2000/svg"
                    viewBox="-8 -5 24 24"
                    width="24"
                    fill="currentColor"
                >
                    <path
                        d="M5.314 7.071l-4.95-4.95A1 1 0 0 1 1.778.707l5.657 5.657a1 1 0 0 1 0 1.414l-5.657 5.657a1 1 0 0 1-1.414-1.414l4.95-4.95z"
                    ></path>
                </svg>
            </Button>
            <!--<Map :zoom="4" :lat="10" :lng="52" />-->
            <Accordion :content="content" />
        </div>
    </main>
    <Footer />
</template>

<script setup lang="ts">
import { Button, Accordion } from './components/Ui';
import Header from './components/Header/Header.vue';
import Footer from './components/Footer/Footer.vue';

const content = [
    {
        title: 'Item 1',
        content: 'lorem ipsum dolor sit amet, consectetur',
    },
    {
        title: 'Item 2',
        content: 'lorem ipsum dolor sit amet, consectetur',
    },
    {
        title: 'Item 3',
        content: 'lorem ipsum dolor sit amet, consectetur',
    },
];
</script>

<style>
#app {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
}
</style>
