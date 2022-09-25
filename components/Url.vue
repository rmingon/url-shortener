<script setup lang="ts">
  import { useQRCode } from '@vueuse/integrations/useQRCode'

  let as_shorten = ref(false)
  let url_shorten = ref('')
  let open_qrcode = ref(false)
  let qrcode = ref('')

  const regex_url = new RegExp(/[-a-zA-Z0-9@:%._\+~#=]{1,256}\.[a-zA-Z0-9()]{1,6}\b([-a-zA-Z0-9()@:%_\+.~#?&//=]*)?/g)

  const is_url = computed(() => url_shorten.value.match(regex_url))

  const hash = () => {
    return Date.now().toString(36);
  }

  const domain = () => {
    return window.location.host
  }

  qrcode = useQRCode(url_shorten)

  const short = () => {
    if (is_url.value) {
      as_shorten.value = true
      url_shorten.value = `${domain()}/${hash()}`
    }
  }

  const reset = () => {
    as_shorten.value = false
    url_shorten.value = ''
  }

  const copyInClipboard = () => {
    navigator.clipboard.writeText(url_shorten.value);
  }
</script>

<template>
  <div class="flex justify-center w-full z-20">
    <div class="flex flex-col w-full bg-white border mx-12 px-6 py-6 rounded shadow-2xl">
      <div class="flex justify-between w-full mb-3 items-center">
        <div class="flex items-center">
          <div class=" text-yellow-400">
            <svg width="16" height="16" viewBox="0 0 21 21"><path fill="text-yellow-400" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" d="m10.5 14.5l-5 3l2-5.131l-4-3.869h5l2-5l2 5h5l-4 4l2 5z"/></svg>
          </div>
          <div class="mr-1">
            Register for more features
          </div>
        </div>
        <div class="flex items-center">
          <div class="mr-1">
            see feature
          </div>
          <div class="border-2 rounded-full cursor-pointer">
            <svg width="24" height="24" viewBox="0 0 24 24"><path fill="currentColor" d="M7.41 8.59L12 13.17l4.59-4.58L18 10l-6 6l-6-6l1.41-1.41z"/></svg>
          </div>
        </div>
      </div>
      <div class="flex w-full justify-between items-center">
        <!--<BasicsSelect :list="['hotdog.dev', 'miaoucat.io']" />-->
        <div class="flex items-center flex-row w-full">
          <div class="border-b border-l border-t p-4 rounded-md" :class="is_url ? 'border-green-500' : 'border-red-500'">
            <svg :class="is_url ? 'stroke-green-500' : 'stroke-red-300'"  width="24" height="24" viewBox="0 0 24 24"><g fill="none" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5"><path d="M14 11.998C14 9.506 11.683 7 8.857 7H7.143C4.303 7 2 9.238 2 11.998c0 2.378 1.71 4.368 4 4.873a5.3 5.3 0 0 0 1.143.124"/><path d="M10 11.998c0 2.491 2.317 4.997 5.143 4.997h1.714c2.84 0 5.143-2.237 5.143-4.997c0-2.379-1.71-4.37-4-4.874A5.304 5.304 0 0 0 16.857 7"/></g></svg>
          </div>
          <div class="border-l h-8"></div>
          <div class="w-full">
            <input v-model="url_shorten" class="w-full border-b border-r border-t border-slate-300 p-4 rounded-md" type="text" placeholder="Paste long url for shorten url : http://domain.com">
          </div>
        </div>
        <button v-if="!as_shorten" @click="short()" class="bg-green-400 duration-200 hover:bg-green-500 hover:shadow-sm active:filter-none active:bg-green-600 py-4 px-16 rounded inline-flex items-center hover:bg-grey ml-4">
          <svg class="mr-4 text-white" width="20" height="20" viewBox="0 0 24 24"><path fill="currentColor" d="M12 6v3l4-4l-4-4v3c-4.42 0-8 3.58-8 8c0 1.57.46 3.03 1.24 4.26L6.7 14.8A5.87 5.87 0 0 1 6 12c0-3.31 2.69-6 6-6zm6.76 1.74L17.3 9.2c.44.84.7 1.79.7 2.8c0 3.31-2.69 6-6 6v-3l-4 4l4 4v-3c4.42 0 8-3.58 8-8c0-1.57-.46-3.03-1.24-4.26z"/></svg>
          <span class="text-white">Shorten</span>
        </button>
        <button v-if="as_shorten" @click="copyInClipboard()" class="bg-red-400 duration-200 hover:bg-red-500 hover:shadow-sm active:filter-none active:bg-green-600 py-4 px-16 rounded inline-flex items-center hover:bg-grey ml-4">
          <svg class="mr-4 text-white" width="20" height="20" viewBox="0 0 24 24"><path fill="currentColor" d="M12 6v3l4-4l-4-4v3c-4.42 0-8 3.58-8 8c0 1.57.46 3.03 1.24 4.26L6.7 14.8A5.87 5.87 0 0 1 6 12c0-3.31 2.69-6 6-6zm6.76 1.74L17.3 9.2c.44.84.7 1.79.7 2.8c0 3.31-2.69 6-6 6v-3l-4 4l4 4v-3c4.42 0 8-3.58 8-8c0-1.57-.46-3.03-1.24-4.26z"/></svg>
          <span class="text-white">Copy</span>
        </button>
        <button v-if="as_shorten" @click="open_qrcode = !open_qrcode" class="bg-red-400 duration-200 hover:bg-red-500 hover:shadow-sm active:filter-none active:bg-green-600 p-4 rounded inline-flex items-center hover:bg-grey ml-4">
          <svg class="text-white" width="22" height="22" viewBox="0 0 24 24"><path fill="currentColor" d="M4 4h6v6H4V4m16 0v6h-6V4h6m-6 11h2v-2h-2v-2h2v2h2v-2h2v2h-2v2h2v3h-2v2h-2v-2h-3v2h-2v-4h3v-1m2 0v3h2v-3h-2M4 20v-6h6v6H4M6 6v2h2V6H6m10 0v2h2V6h-2M6 16v2h2v-2H6m-2-5h2v2H4v-2m5 0h4v4h-2v-2H9v-2m2-5h2v4h-2V6M2 2v4H0V2a2 2 0 0 1 2-2h4v2H2m20-2a2 2 0 0 1 2 2v4h-2V2h-4V0h4M2 18v4h4v2H2a2 2 0 0 1-2-2v-4h2m20 4v-4h2v4a2 2 0 0 1-2 2h-4v-2h4Z"/></svg>
        </button>
        <button v-if="as_shorten" @click="reset()" class="bg-red-400 duration-200 hover:bg-red-500 hover:shadow-sm active:filter-none active:bg-green-600 p-4 rounded inline-flex items-center hover:bg-grey ml-4">
          <svg class="text-white" width="22" height="22" viewBox="0 0 24 24"><path fill="currentColor" d="M17.65 6.35A7.958 7.958 0 0 0 12 4a8 8 0 0 0-8 8a8 8 0 0 0 8 8c3.73 0 6.84-2.55 7.73-6h-2.08A5.99 5.99 0 0 1 12 18a6 6 0 0 1-6-6a6 6 0 0 1 6-6c1.66 0 3.14.69 4.22 1.78L13 11h7V4l-2.35 2.35Z"/></svg>
        </button>
      </div>
      <div v-if="open_qrcode" class="flex justify-center">
        <img class="shadow mt-2" :src="qrcode" alt="QR Code" />
      </div>
    </div>
  </div>
</template>