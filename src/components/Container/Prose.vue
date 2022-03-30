<template>
    <div class="prose" v-html="content">
        <slot />
    </div>
</template>

<script lang="ts" setup>
const props = defineProps({
    content: {
        type: String,
    },
});
</script>

<style>
.prose {
    color: var(--color-text);
}
.prose h2,
.prose h3,
.prose h4 {
    margin-bottom: 30px;
    font-weight: 600;
}
.prose h2 {
    font-size: 24px;
}
.prose h3 {
    font-size: 20px;
}
.prose h4 {
    font-size: 16px;
}
.prose p {
    margin-bottom: 30px;
}
.prose a {
    color: var(--color-primary-default);
    text-decoration: underline;
}
.prose ul {
    margin-bottom: 30px;
    padding-inline: 16px;
}
.prose ul li {
    position: relative;
}
.prose ul li::before {
    content: '';
    position: absolute;
    left: -16px;
    top: 10px;
    border-radius: 9999px;
    padding: 3px;
    background: var(--color-text);
}
.prose table {
    margin-bottom: 30px;
}
.prose th {
    text-align: left;
    padding-inline: 12px;
    padding-top: 5px;
    min-width: 50px;
    font-weight: 600;
}
.prose td {
    padding-inline: 12px;
    padding-top: 5px;
    min-width: 50px;
}
</style>
