<script setup>
  import { useElementVisibility } from '@vueuse/core'

  const target = ref(null)
  const targetIsVisible = useElementVisibility(target)  
</script>

<template>
  <div class="bg-white flex w-full flex-col text-center pt-12 pb-10 justify-center items-center">
    <div ref="target" class="montserrat-extra-bold text-3xl text-center">
      Some features
    </div>
    <div class="w-32 border-b-2 border-sky-500 mt-2"></div>
    <Transition>
      <div v-if="targetIsVisible" class="text-xl px-12 mt-8">
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Sapiente, esse minus ipsa, deserunt maxime quia ipsam obcaecati perferendis quibusdam ex illum a animi ducimus harum nisi accusamus praesentium sint. Nihil?
      </div>
    </Transition>
  </div>
</template>

<style scoped>
  .v-enter-active,
  .v-leave-active {
    transition: opacity 4s ease;
  }

  .v-enter-from,
  .v-leave-to {
    opacity: 0;
  }
</style>