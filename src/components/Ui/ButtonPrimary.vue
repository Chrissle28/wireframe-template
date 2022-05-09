<template>
    <component
        :is="getTag()"
        :href="routeUrl"
        class="font-semibold inline-flex items-center focus:outline-none focus:ring-4 focus:ring-primary-light justify-center py-2.5 border-2"
        :class="{
            'px-5': !square,
            'px-2.5': square,
            'text-white border-primary bg-primary': !disabled && !outlined,
            'text-white pointer-events-none border-primary bg-primary opacity-40':
                disabled && !outlined,
            'text-primary border-primary bg-white': !disabled && outlined,
            'text-primary pointer-events-none border-primary bg-white opacity-40':
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
