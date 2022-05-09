<template>
    <div class="relative w-full px-8 py-16 mt-24 bg-white shadow-lg">
        <div
            v-if="contact.image"
            class="absolute -translate-x-1/2 -top-24 w-36 h-36 left-1/2"
        >
            <img
                class="object-cover w-full h-full rounded-full"
                :src="contact.image"
                :alt="contact.name"
            />
        </div>
        <div class="mb-3 text-lg font-semibold text-primary">
            {{ contact.name }}
        </div>
        <div class="mb-4">
            {{ contact.description }}
        </div>
        <div class="">
            {{ contact.phone }}
        </div>
        <a :href="`mailto:${contact.email}`" class="text-secondary">
            {{ contact.email }}
        </a>
    </div>
</template>

<script lang="ts" setup>
const props = defineProps({
    contact: {
        type: Object,
        required: true,
    },
});
</script>
