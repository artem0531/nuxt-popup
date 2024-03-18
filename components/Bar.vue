<template>
  <PopupBar v-if="!hasAccess">
    <div class="flex items-center justify-center space-x-4">
      <span class="text-black/70 text-sm">AI is expensive to run. Purchase a 7-day pass to get unlimited designs</span>
      <ButtonDark size="xs" @click="setModalStatus('upgrade', true)">
        Get 7 days access
      </ButtonDark>
    </div>
  </PopupBar>
</template>

<script>
export default {

}
</script>

<style>

</style>
