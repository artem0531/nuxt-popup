<template>
  <div class="flex items-start justify-start space-x-4">
    <div class="w-10 h-10 block flex flex-shrink-0 justify-center items-center rounded-lg" :style="`background-color:${background}`">
      <slot />
    </div>
    <div class="flex flex-col">
      <div class="flex justify-start items-center contents-center">
        <h3 class="font-semibold m-0">
          {{ title }}
        </h3>
        <div v-if="soon" class="ml-2 bg-gray-300 text-[9px] p-1 flex-shrink-1 font-bold uppercase rounded-md">
          Soon
        </div>
      </div>
      <p class="text-sm text-gray-700">
        {{ description }}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true
    },
    description: {
      type: String,
      required: true
    },
    background: {
      type: String,
      default: '#222'
    },
    soon: {
      type: Boolean,
      default: false
    }
  }

}
</script>

<style>

</style>
