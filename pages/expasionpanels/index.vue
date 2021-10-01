<template>
  <div class="page-expasion-panels">
    <!-- <ExampleOne :items-panel="itemsPanel" /> -->
    <ExampleTwo />
  </div>
</template>

<script lang="ts">
import { defineComponent } from '@nuxtjs/composition-api'

// Importa componentes
import { ExampleTwo } from '@/components/ExpasionPanels'

export default defineComponent({
  components: {
    ExampleTwo
  }
})
</script>

<style lang="scss" scoped>
  @import './style.scss';
</style>
