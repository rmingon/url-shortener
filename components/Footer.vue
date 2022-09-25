<template>
  <div class="px-14 mb-10">
    <div class="flex flex-row">
      <div class="basis-1/2 flex justify-center items-center">
        <div class="flex flex-col items-center justify-center cursor-pointer bg-slate-50 py-4 px-6 w-48 rounded hover:shadow-xl mt-5 rotate-6 h-16">
          <div>
            Follow me !
          </div>
          <div>
            <svg class="" width="32" height="32" viewBox="0 0 24 24"><path d="M5 3h14a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2h-4.44c-.32-.07-.33-.68-.33-.89l.01-2.47c0-.84-.29-1.39-.61-1.67c2.01-.22 4.11-.97 4.11-4.44c0-.98-.35-1.79-.92-2.42c.09-.22.4-1.14-.09-2.38c0 0-.76-.23-2.48.93c-.72-.2-1.48-.3-2.25-.31c-.76.01-1.54.11-2.25.31c-1.72-1.16-2.48-.93-2.48-.93c-.49 1.24-.18 2.16-.09 2.38c-.57.63-.92 1.44-.92 2.42c0 3.47 2.1 4.22 4.1 4.47c-.26.2-.49.6-.57 1.18c-.52.23-1.82.63-2.62-.75c0 0-.48-.86-1.38-.93c0 0-.88 0-.06.55c0 0 .59.28 1 1.32c0 0 .52 1.75 3.03 1.21l.01 1.53c0 .21-.02.82-.34.89H5a2 2 0 0 1-2-2V5a2 2 0 0 1 2-2z" fill="currentColor"/></svg>
          </div>
        </div>
      </div>
      <div class="basis-1/2">
        <div class="text-center text-2xl text-white my-2">
          Contact us !
        </div>
        <form action="">
          <input type="text" name="" id="" placeholder="Name" class="w-full border-b border-r border-t border-slate-300 p-4 rounded-md my-2">
          <input type="text" name="" id="" placeholder="Email" class="w-full border-b border-r border-t border-slate-300 p-4 rounded-md my-2">
          <textarea name="" id="" cols="30" rows="10" class="w-full border-b border-r border-t border-slate-300 p-4 rounded-md my-2"></textarea>
          <button type="submit" class="flex flex-row items-center rounded-lg shadow p-4 hover:shadow-lg duration-200 bg-white">
            <div class="flex items-center cursor-pointer mr-2">
              <svg width="32" height="32" viewBox="0 0 24 24"><path fill="currentColor" d="m4 6.03l7.5 3.22l-7.5-1V6.03m7.5 8.72L4 17.97v-2.22l7.5-1M2 3v7l15 2l-15 2v7l21-9L2 3Z"/></svg>
            </div>
            <div class="flex flex-col w-full">
              <div class="MontserratBold">
                Send
              </div>
            </div>
            <div class="flex flex-col ml-2">
              <div class="border-2 rounded-full cursor-pointer -rotate-90">
                <svg width="24" height="24" viewBox="0 0 24 24"><path fill="currentColor" d="M7.41 8.59L12 13.17l4.59-4.58L18 10l-6 6l-6-6l1.41-1.41z"/></svg>
              </div>
            </div>
          </button>
        </form>
      </div>
    </div>
  </div>
</template>