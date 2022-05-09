<template>
    <div class="w-full mt-24 bg-white shadow-lg">
        <div v-if="announcement.image" class="w-full h-52">
            <img
                class="object-cover w-full h-full"
                :src="announcement.image"
                :alt="announcement.title"
            />
        </div>
        <div
            class="flex flex-col p-8"
            :class="{ 'h-full': !announcement.image }"
        >
            <div class="text-secondary mb-3.5">
                {{ announcement.date }}
            </div>
            <div class="mb-3 text-lg font-semibold text-primary">
                {{ announcement.title }}
            </div>
            <div>
                {{ announcement.description }}
            </div>
            <div
                :class="{
                    'mt-auto': !announcement.image,
                    'mt-10': announcement.image,
                }"
            >
                <ButtonPrimary :href="announcement.link" outlined>
                    Read More
                </ButtonPrimary>
            </div>
        </div>
    </div>
</template>

<script lang="ts" setup>
import { ButtonPrimary } from '../Ui';

const props = defineProps({
    announcement: {
        type: Object,
        required: true,
    },
});
</script>
