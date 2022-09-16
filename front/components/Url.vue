<script setup lang="ts">
  import { TransitionPresets, useTransition } from '@vueuse/core'

  let rotate = ref(0)

  const output = useTransition(rotate, {
    duration: 1000,
    transition: TransitionPresets.easeInOutCubic,
  })
</script>

<template>
  <div class="flex justify-center w-full">
    <div class="flex flex-col w-full bg-white border mx-10 px-4 py-4 rounded">
      <div class="flex justify-between w-full mb-3 items-center">
        <div class="flex items-center">
          <div class=" text-yellow-400">
            <svg width="16" height="16" viewBox="0 0 21 21"><path fill="text-yellow-400" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" d="m10.5 14.5l-5 3l2-5.131l-4-3.869h5l2-5l2 5h5l-4 4l2 5z"/></svg>
          </div>
          <div class="mr-1">
            Register for more feature
          </div>
        </div>
        <div class="flex items-center">
          <div class="mr-1 MontserratBold">
            see feature
          </div>
          <div class="border-2 rounded-full">
            <svg width="24" height="24" viewBox="0 0 24 24"><path fill="currentColor" d="M7.41 8.59L12 13.17l4.59-4.58L18 10l-6 6l-6-6l1.41-1.41z"/></svg>
          </div>
        </div>
      </div>
      <div class="flex w-full justify-between items-center">
        <!--<BasicsSelect :list="['hotdog.dev', 'miaoucat.io']" />-->
        <div class="flex items-center flex-row w-full">
          <div class="border-b border-l border-t border-slate-300 p-4 rounded-md">
            <svg width="24" height="24" viewBox="0 0 24 24"><g fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5"><path d="M14 11.998C14 9.506 11.683 7 8.857 7H7.143C4.303 7 2 9.238 2 11.998c0 2.378 1.71 4.368 4 4.873a5.3 5.3 0 0 0 1.143.124"/><path d="M10 11.998c0 2.491 2.317 4.997 5.143 4.997h1.714c2.84 0 5.143-2.237 5.143-4.997c0-2.379-1.71-4.37-4-4.874A5.304 5.304 0 0 0 16.857 7"/></g></svg>
          </div>
          <div class="border-l h-8"></div>
          <div class="w-full">
            <input class="w-full border-b border-r border-t border-slate-300 p-4 rounded-md" type="text" placeholder="Paste long url for shorten url">
          </div>
        </div>
        <button class="bg-green-400 duration-200 hover:bg-green-500 hover:shadow-sm active:filter-none active:bg-green-600 py-4 px-16 rounded inline-flex items-center hover:bg-grey ml-4">
          <svg class="mr-4 text-white" :class="`rotate-[${rotate}]`" width="20" height="20" viewBox="0 0 24 24"><path fill="currentColor" d="M12 6v3l4-4l-4-4v3c-4.42 0-8 3.58-8 8c0 1.57.46 3.03 1.24 4.26L6.7 14.8A5.87 5.87 0 0 1 6 12c0-3.31 2.69-6 6-6zm6.76 1.74L17.3 9.2c.44.84.7 1.79.7 2.8c0 3.31-2.69 6-6 6v-3l-4 4l4 4v-3c4.42 0 8-3.58 8-8c0-1.57-.46-3.03-1.24-4.26z"/></svg>
          <span class="text-white">Shorten</span>
        </button>
      </div>
    </div>
  </div>
</template>