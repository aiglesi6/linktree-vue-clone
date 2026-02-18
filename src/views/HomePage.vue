<script setup>
import { ref } from 'vue'
import LinkCard from '@/components/LinkCard.vue'

const profile = ref({
  name: 'Alicia Garza',
  slogan: 'Full Stack Developer and Student',
  avatar: 'https://api.dicebear.com/9.x/open-peeps/svg?seed=Aneka',
  links: [
    {
      id: 1,
      title: 'GitHub',
      url: 'https://github.com/aiglesi6',
      icon: 'code',
      description: 'Check out my projects',
    },
    {
      id: 2,
      title: 'LinkedIn',
      url: 'https://www.linkedin.com/in/alicia-garza-1a00643b2/',
      icon: 'briefcase',
      description: 'Connect with me professionally',
    },
    {
      id: 3,
      title: 'Expense Splitter',
      url: 'https://expense-splitter-vue.aiglesi6.workers.dev/',
      icon: 'dollar',
      description: 'Calculate your debts',
    },
    {
      id: 4,
      title: 'Expense Splitter - GitHub',
      url: 'https://github.com/aiglesi6/expense-splitter/tree/main/01-ExpensesSplitter',
      icon: 'dollar',
      description: 'Source code for Vue application',
    },
  ],
})
</script>

<template>
  <main class="flex min-h-screen flex-col items-center justify-center bg-gray-700 px-4 py-8">
    <!-- Profile Header -->
    <div class="mb-8 flex flex-col items-center text-center">
      <div
        class="mb-4 h-24 w-24 overflow-hidden rounded-full border-4 border-blue-500 shadow-lg shadow-blue-700/20 sm:h-32 sm:w-32"
      >
        <img
          :src="profile.avatar"
          :alt="profile.name"
          class="h-full w-full object-cover"
        />
      </div>
      <h1 class="mb-2 font-display text-2xl font-bold text-blue-200 sm:text-3xl">
        {{ profile.name }}
      </h1>
      <p class="max-w-xs text-gray-300 sm:text-lg">{{ profile.slogan }}</p>
    </div>

    <!--- Link List--->
    <div class="flex w-full max-w-md flex-col gap-4">
      <LinkCard
        v-for="link in profile.links"
        :key="link.id"
        :title="link.title"
        :url="link.url"
        :description="link.description"
        :icon="link.icon"
      />
    </div>

    <!--- Navigate to Info -->
    <RouterLink
      to="/info"
      class="mt-8 text-sm text-gray-400 underline-offset-4 transition-colors duration-300 hover:text-blue-400 hover:underline"
      >About Me →
    </RouterLink>
  </main>
</template>
