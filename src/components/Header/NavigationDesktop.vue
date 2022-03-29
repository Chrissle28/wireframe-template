<template>
    <ul class="hidden lg:flex items-end h-[100px] flex-wrap gap-10">
        <li v-for="entry in navigation">
            <a
                v-if="!hasChildren(entry)"
                :href="entry.link"
                class="font-semibold"
            >
                {{ entry.name }}
            </a>
            <Popover
                class="relative"
                v-if="hasChildren(entry)"
                v-slot="{ open }"
            >
                <PopoverButton class="font-semibold flex items-center gap-2">
                    <span>{{ entry.name }}</span>
                    <svg
                        v-if="hasChildren(entry)"
                        xmlns="http://www.w3.org/2000/svg"
                        viewBox="-5 -8 24 24"
                        width="16"
                        fill="currentColor"
                        class="transition-transform duration-300"
                        :class="{ 'rotate-180': open }"
                    >
                        <path
                            d="M7.071 5.314l4.95-4.95a1 1 0 1 1 1.414 1.414L7.778 7.435a1 1 0 0 1-1.414 0L.707 1.778A1 1 0 1 1 2.121.364l4.95 4.95z"
                        ></path>
                    </svg>
                </PopoverButton>
                <PopoverPanel
                    class="absolute left-1/2 -translate-x-1/2 top-full"
                >
                    <ul
                        class="mt-2 relative text-left min-w-[160px] bg-secondary p-4 flex flex-col gap-5"
                    >
                        <div
                            class="menu-arrow absolute -top-2 left-1/2 -translate-x-1/2"
                        ></div>
                        <li as="li" v-for="child in entry.children">
                            <a
                                :href="child.link"
                                class="font-semibold text-white"
                            >
                                {{ child.name }}
                            </a>
                        </li>
                    </ul>
                </PopoverPanel>
            </Popover>
        </li>
    </ul>
</template>

<script lang="ts" setup>
import { Menu, MenuButton, MenuItems, MenuItem } from '@headlessui/vue';
import { Popover, PopoverButton, PopoverPanel } from '@headlessui/vue';

const props = defineProps({
    navigation: {
        type: Object,
    },
});

console.log(props.navigation);

const hasChildren = (entry: any) => {
    if (!entry.children || entry.children.length <= 0) {
        return false;
    }
    return true;
};
</script>

<style>
.menu-arrow {
    width: 0;
    height: 0;
    border-left: 10px solid transparent;
    border-right: 10px solid transparent;
    border-bottom: 10px solid var(--color-secondary-default);
}
</style>
