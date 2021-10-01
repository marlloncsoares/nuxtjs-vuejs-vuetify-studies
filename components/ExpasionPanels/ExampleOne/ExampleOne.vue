<template>
  <div class="container">
    <v-expansion-panels accordion>
      <v-expansion-panel>
        <v-expansion-panel-header>
          <v-checkbox
            :v-model="itemsPanel.header.value"
            :label="itemsPanel.header.label"
          />
        </v-expansion-panel-header>
        <v-expansion-panel-content>
          <v-checkbox
            v-for="(item, index) in itemsPanel.items"
            :key="index"
            :v-model="item.value"
            :label="item.label"
            @click="log"
          />
        </v-expansion-panel-content>
      </v-expansion-panel>
    </v-expansion-panels>
  </div>
</template>

<script lang="ts">
import { defineComponent } from '@nuxtjs/composition-api'

export default defineComponent({
  props: {
    itemsPanel: {
      type: Object,
      default: null
    }
  },
  setup (props) {
    const log = () => {
      console.log(props)
    }

    return {
      log
    }
  }
})
</script>

<style lang="scss" scoped>
  @import './style.scss';
</style>
