<template>
    <div class="w-full mt-24 bg-white shadow-lg">
        <div v-if="image" class="w-full h-52">
            <img class="object-cover w-full h-full" :src="image" :alt="title" />
        </div>
        <div class="flex flex-col p-8" :class="{ 'h-full': !image }">
            <div class="mb-2 text-lg font-semibold">
                {{ title }}
            </div>
            <div>
                {{ description }}
            </div>
            <div
                :class="{
                    'mt-auto': !image,
                    'mt-10': image,
                }"
            >
                <ButtonPrimary :href="link" outlined>
                    {{ linkText }}
                </ButtonPrimary>
            </div>
        </div>
    </div>
</template>

<script lang="ts" setup>
import { ButtonPrimary } from '../Ui';

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
