<template>
    <div class="bg-white">
        <div class="mx-auto max-w-7xl px-6 lg:px-8">
            <div class="mx-auto max-w-4xl sm:text-center">
                <!-- <h2 class="text-base font-semibold leading-7 text-indigo-600">Pricing</h2> -->
                <p class="mt-2 text-4xl font-bold tracking-tight text-gray-900 sm:text-5xl">Choose the right plan
                    for&nbsp;you</p>
            </div>
            <p class="mx-auto mt-6 max-w-2xl text-lg leading-8 text-gray-600 sm:text-center">Distinctio et nulla eum soluta
                et neque labore quibusdam. Saepe et quasi iusto modi velit ut non voluptas in. Explicabo id ut laborum.</p>
            <div class="mt-20 flow-root">
                <div
                    class="isolate -mt-16 grid max-w-sm grid-cols-1 gap-y-16 divide-y divide-gray-100 sm:mx-auto lg:-mx-8 lg:mt-0 lg:max-w-none lg:grid-cols-3 lg:divide-x lg:divide-y-0 xl:-mx-4">
                    <div v-for="tier in tiers" :key="tier.id" class="pt-16 lg:px-8 lg:pt-0 xl:px-14">
                        <h3 :id="tier.id" class="text-base font-semibold leading-7 text-gray-900">{{ tier.name }}</h3>
                        <p class="mt-6 flex items-baseline gap-x-1">
                            <span class="text-5xl font-bold tracking-tight text-gray-900">{{ tier.price.monthly }}</span>
                            <span class="text-sm font-semibold leading-6 text-gray-600">/month</span>
                        </p>
                        <p class="mt-3 text-sm leading-6 text-gray-500">{{ tier.price.annually }} per month if paid annually
                        </p>
                        <a :href="tier.href" :aria-describedby="tier.id"
                            class="mt-10 block rounded-md bg-indigo-600 px-3 py-2 text-center text-sm font-semibold leading-6 text-white shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600">Buy
                            plan</a>
                        <p class="mt-10 text-sm font-semibold leading-6 text-gray-900">{{ tier.description }}</p>
                        <ul role="list" class="mt-6 space-y-3 text-sm leading-6 text-gray-600">
                            <li v-for="feature in tier.features" :key="feature" class="flex gap-x-3">
                                <CheckCircleIcon class="h-6 w-5 flex-none text-indigo-600" aria-hidden="true" />
                                {{ feature }}
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
  
<script setup>
import { CheckCircleIcon } from '@heroicons/vue/20/solid'

const tiers = [
    {
        name: 'Basic',
        id: 'tier-basic',
        href: '#',
        price: { monthly: '$15', annually: '$12' },
        description: 'Everything necessary to get started.',
        features: ['5 products', 'Up to 1,000 subscribers', 'Basic analytics', '48-hour support response time'],
    },
    {
        name: 'Essential',
        id: 'tier-essential',
        href: '#',
        price: { monthly: '$30', annually: '$24' },
        description: 'Everything in Basic, plus essential tools for growing your business.',
        features: [
            '25 products',
            'Up to 10,000 subscribers',
            'Advanced analytics',
            '24-hour support response time',
            'Marketing automations',
        ],
    },
    {
        name: 'Growth',
        id: 'tier-growth',
        href: '#',
        price: { monthly: '$60', annually: '$48' },
        description: 'Everything in Essential, plus collaboration tools and deeper insights.',
        features: [
            'Unlimited products',
            'Unlimited subscribers',
            'Advanced analytics',
            '1-hour, dedicated support response time',
            'Marketing automations',
            'Custom reporting tools',
        ],
    },
]
</script>