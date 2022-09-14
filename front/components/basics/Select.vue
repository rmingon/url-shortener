<script setup lang="ts">
  let open = ref<boolean>(false)
  let selected = ref<string>("")
  let listOfElement = ref<string[]>(['test1', 'YOYO'])
</script>

<template>
  <div class="flex-auto flex flex-col items-center h-64">
    <div class="flex flex-col items-center relative">
        <div class="w-full">
            <div class="my-2 bg-white p-1 flex border border-gray-200">
                <div class="flex flex-auto flex-wrap"></div>
                <input class="p-1 px-2 appearance-none outline-none w-full text-gray-800" :value="selected">
                <div>
                  <button @click="selected = ''" class="cursor-pointer w-6 h-full flex items-center text-gray-400 outline-none focus:outline-none">
                      <svg xmlns="http://www.w3.org/2000/svg" width="100%" height="100%" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-x w-4 h-4">
                          <line x1="18" y1="6" x2="6" y2="18"></line>
                          <line x1="6" y1="6" x2="18" y2="18"></line>
                      </svg>
                  </button>
                </div>
                <div @click="open = true" class="text-gray-300 w-8 py-1 pl-2 pr-1 border-l flex items-center border-gray-200 cursor-pointer">
                    <button class="cursor-pointer w-6 h-6 text-gray-600 outline-none focus:outline-none">
                        <svg xmlns="http://www.w3.org/2000/svg" width="100%" height="100%" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-chevron-up w-4 h-4">
                            <polyline points="18 15 12 9 6 15"></polyline>
                        </svg>
                    </button>
                </div>
            </div>
        </div>
        <div v-if="open" class="absolute shadow top-100 z-40 w-full max-h-select overflow-y-auto">
            <div class="flex flex-col w-full" v-for="el in listOfElement">
                <div @click="selected = el" class="cursor-pointer w-full border-gray-100 rounded-t border-b hover:bg-teal-100" style="">
                    <div class="flex w-full items-center p-2 pl-2 border-transparent bg-white border-l-2 relative hover:bg-teal-600 hover:text-teal-100 hover:border-teal-600">
                        <div class="w-full items-center flex">
                            <div class="mx-2 leading-6">{{ el }}</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</div>
</template>

<style scoped>
  .top-100 {top: 100%}
  .bottom-100 {bottom: 100%}
  .max-h-select {
      max-height: 300px;
  }
</style>