<template>
    <Disclosure as="nav" class="bg-gray-800" v-slot="{ open }">
        <div class="mx-auto max-w-7xl px-2 sm:px-6 lg:px-8">
            <div class="relative flex h-16 items-center justify-between">
                <div class="absolute inset-y-0 left-0 flex items-center sm:hidden">
                    <!-- Mobile menu button-->
                    <DisclosureButton
                        class="relative inline-flex items-center justify-center rounded-md p-2 text-gray-400 hover:bg-gray-700 hover:text-white focus:outline-none focus:ring-2 focus:ring-inset focus:ring-white">
                        <span class="absolute -inset-0.5" />
                        <span class="sr-only">Open main menu</span>
                        <Bars3Icon v-if="!open" class="block h-6 w-6" aria-hidden="true" />
                        <XMarkIcon v-else class="block h-6 w-6" aria-hidden="true" />
                    </DisclosureButton>
                </div>
                <div class="flex flex-1 items-center justify-center sm:items-stretch sm:justify-start">
                    <div class="flex flex-shrink-0 items-center">
                        <a href="/">
                            <img class="h-8 w-auto" src="https://i.pinimg.com/originals/8e/71/3c/8e713ce65aacea777d8065a5c80f6307.png"
                            alt="Your Company" />
                        </a>
                    </div>
                    <div class="hidden sm:ml-6 sm:block">
                        <div class="flex space-x-4">
                            <a v-for="item in navigation" :key="item.name" @click="navigateTo(item.href)"
                                :class="[item.current ? 'hover:bg-gray-700 text-white' : 'text-gray-300 hover:bg-gray-700 hover:text-white', 'rounded-md px-3 py-2 text-sm font-medium']"
                                :aria-current="item.current ? 'page' : undefined">{{ item.name }}</a>
                        </div>
                    </div>
                </div>
                <div class="absolute inset-y-0 right-0 flex items-center pr-2 sm:static sm:inset-auto sm:ml-6 sm:pr-0">
                    <!-- Profile dropdown -->
                    <Menu as="div" class="relative ml-3">
                        <div>
                            <MenuButton
                                class="relative flex rounded-full bg-gray-800 text-sm focus:outline-none focus:ring-2 focus:ring-white focus:ring-offset-2 focus:ring-offset-gray-800">
                                <span class="absolute -inset-1.5" />
                                <span class="sr-only">Open user menu</span>
                                <img class="h-8 w-8 rounded-full"
                                    src="https://preview.redd.it/funniest-cat-pictures-you-have-v0-cvk0vuc0hj5a1.jpg?width=640&crop=smart&auto=webp&s=15b35fec711a4ad3fa71dad7d7850d0299c59367"
                                    alt="" />
                            </MenuButton>
                        </div>
                    </Menu>
                </div>
            </div>
        </div>
    </Disclosure>
</template>

<script setup>
import { Disclosure, DisclosureButton, DisclosurePanel, Menu, MenuButton, MenuItem, MenuItems } from '@headlessui/vue'
import { Bars3Icon, BellIcon, XMarkIcon } from '@heroicons/vue/24/outline'

const navigation = [
    { name: 'Home', href: '/home', current: true },
    { name: 'Team', href: '/team', current: false },
    { name: 'Prices', href: '/prices', current: false },
    { name: 'FAQ', href: '/faq', current: false },
    { name: 'Contact', href: '/contact', current: false },

]
</script>