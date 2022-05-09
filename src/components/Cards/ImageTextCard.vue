<template>
    <div class="w-full mt-24 bg-white shadow-lg">
        <div v-if="image" class="w-full h-52">
            <img class="object-cover w-full h-full" :src="image" :alt="title" />
        </div>
        <div class="p-8">
            <div class="text-lg font-semibold">
                {{ title }}
            </div>
            <div>
                {{ description }}
            </div>
            <ButtonSecondary class="mt-10" :href="link" outlined>
                {{ linkText }}
            </ButtonSecondary>
        </div>
    </div>
</template>

<script lang="ts" setup>
import { ButtonSecondary } from '../Ui';

const props = defineProps({
    image: {
        type: String,
    },
    title: {
        type: String,
    },
    description: {
        type: String,
    },
    link: {
        type: String,
    },
    linkText: {
        type: String,
        default: 'Klick Here',
    },
});
</script>
