<template>
  <div class="flex justify-center w-full">
    <div class="flex w-full justify-between items-center bg-white border mx-10 px-3 py-4">
      <BasicsSelect :list="['hotdog.dev', 'miaoucat.io']" />
      <div class="relative text-gray-600 focus-within:text-gray-400 w-full">
        <span class="absolute inset-y-0 left-0 flex items-center pl-2">
          <button type="submit" class="p-1 focus:outline-none focus:shadow-outline">
            <svg width="32" height="32" viewBox="0 0 24 24"><path fill="currentColor" d="M3.9 12c0-1.71 1.39-3.1 3.1-3.1h4V7H7c-2.76 0-5 2.24-5 5s2.24 5 5 5h4v-1.9H7c-1.71 0-3.1-1.39-3.1-3.1zM8 13h8v-2H8v2zm9-6h-4v1.9h4c1.71 0 3.1 1.39 3.1 3.1s-1.39 3.1-3.1 3.1h-4V17h4c2.76 0 5-2.24 5-5s-2.24-5-5-5z"/></svg>
          </button>
        </span>
        <input type="search" name="q" class="py-2 text-sm text-white bg-gray-900 rounded-md pl-10 focus:outline-none focus:bg-white focus:text-gray-900" placeholder="Search..." autocomplete="off">
      </div>
      <button class="bg-green-400 py-2 px-4 rounded inline-flex items-center hover:bg-grey">
        <svg class="mr-10 text-white" width="20" height="20" viewBox="0 0 24 24"><path fill="currentColor" d="M12 6v3l4-4l-4-4v3c-4.42 0-8 3.58-8 8c0 1.57.46 3.03 1.24 4.26L6.7 14.8A5.87 5.87 0 0 1 6 12c0-3.31 2.69-6 6-6zm6.76 1.74L17.3 9.2c.44.84.7 1.79.7 2.8c0 3.31-2.69 6-6 6v-3l-4 4l4 4v-3c4.42 0 8-3.58 8-8c0-1.57-.46-3.03-1.24-4.26z"/></svg>
        <span class="text-white">Shorten</span>
      </button>
    </div>
  </div>
</template>