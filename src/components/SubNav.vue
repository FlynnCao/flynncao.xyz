<script setup lang="ts">
import { useRoute } from 'vue-router'
import { categoryName, englishOnly, techOnly } from '../logics'

const inactiveStyle = 'opacity-20 hover:opacity-50 font-400'
const activeStyle = 'opacity-100 !font-600'

const route = useRoute()
const options: string[] = [
  'All',
  'Code',
  'Productivity',
  'Computer Science',
  'Linguistics',
  'Personal',
  'Writing',
]
</script>

<template>
  <div class="prose m-auto select-none animate-none! op100!">
    <div mb-0 flex="~ gap2 sm:gap3 wrap" text-xl sm:text-3xl>
      <button flex="~ gap1" items-center mb2 op30 text-sm @click="englishOnly = !englishOnly">
        <div :i="englishOnly ? 'carbon-checkbox-checked' : 'carbon-checkbox'" />
        English Only
      </button>
      <button flex="~ gap1" items-center mb2 op30 text-sm @click="techOnly = !techOnly">
        <div :i="techOnly ? 'carbon-checkbox-checked' : 'carbon-checkbox'" />
        Tech Only
      </button>
      <select id="grid-state" v-model="categoryName" class="block appearance-none w-full border dark:border-gray-700 dark:text-gray-200 border-gray-200 text-gray-700 py-3 px-4 pr-8 rounded leading-tight focus:outline-none focus:bg-white dark:focus:bg-black focus:border-gray-500 dark:bg-black">
        <option v-for="item in options" :key="item" :value="item">
          {{ item }}
        </option>
      </select>
    </div>

    <!-- <div mb-0 flex="~ gap2 sm:gap3 wrap" text-xl sm:text-3xl>
      <RouterLink to="/posts" class="!border-none" w-17 :class="route.path === '/posts' ? activeStyle : inactiveStyle">
        Blog
      </RouterLink>
      <RouterLink to="/talks" class="!border-none" w-20 :class="route.path === '/talks' ? activeStyle : inactiveStyle">
        Talks
      </RouterLink>
      <RouterLink
        to="/podcasts" class="!border-none" w-35
        :class="route.path === '/podcasts' ? activeStyle : inactiveStyle"
      >
        Podcasts
      </RouterLink>
      <RouterLink
        to="/streams" class="!border-none" w-40
        :class="route.path === '/streams' ? activeStyle : inactiveStyle"
      >
        Streams
      </RouterLink>
    </div> -->
  </div>
</template>
