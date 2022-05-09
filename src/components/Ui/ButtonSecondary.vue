<template>
    <component
        :is="getTag()"
        :href="routeUrl"
        class="font-semibold inline-flex items-center focus:outline-none focus:ring-4 focus:ring-secondary-light justify-center py-2.5 border-2"
        :class="{
            'px-5': !square,
            'px-2.5': square,
            'text-white border-secondary bg-secondary': !disabled && !outlined,
            'text-white pointer-events-none border-secondary bg-secondary opacity-40':
                disabled && !outlined,
            'text-secondary border-secondary bg-white': !disabled && outlined,
            'text-secondary pointer-events-none border-secondary bg-white opacity-40':
                disabled && outlined,
        }"
    >
        <slot />
    </component>
</template>

<script lang="ts" setup>
import { computed, useAttrs } from 'vue';

const props = defineProps({
    disabled: {
        default: false,
        type: Boolean,
    },
    route: {
        type: String,
        default: null,
    },
    outlined: {
        type: Boolean,
        default: false,
    },
    square: {
        default: false,
        type: Boolean,
    },
});

const attrs = useAttrs();

const getTag = () => {
    if ('href' in attrs || props.route) {
        if (attrs.target == '_blank') {
            return 'a';
        }
        return 'a';
    }
    return 'button';
};

const routeUrl = computed(() => {
    if (props.route) {
        return props.route;
    }
});
</script>
