<template>
  <Popup v-if="showModal" size="2xl" class="z-[999]" @closeModal="closeModal">
    <UpgradeBlock />
  </Popup>
</template>

<script>
export default {
  computed: {
    showModal () {
      return this.$store.state.modal.upgrade
    }
  },
  watch: {
    showModal (newValue) {
      if (newValue === true) {
        // this.trackEvent({ name: 'checkout:upgrade_modal' })
      }
    }
  },
  methods: {
    closeModal () {
      this.setModalStatus('upgrade', false)
    }
  }

}
</script>

<style>

</style>
