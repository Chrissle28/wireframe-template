<template>
    <!-- TODO: Check structure of social links later with real data -->
    <div class="flex flex-wrap items-center gap-4">
        <a target="_blank" href="" v-for="link in links"> Social Link Icon </a>
    </div>
</template>

<script lang="ts" setup>
const props = defineProps({
    links: {
        type: Object,
        required: true,
    },
});
</script>
