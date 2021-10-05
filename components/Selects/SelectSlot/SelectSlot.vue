<template>
  <v-container fluid>
    <v-select
      v-model="e11"
      solo
      dense
      :items="people"
      label="Select"
      item-text="name"
      item-value="name"
      multiple
      @input="processaSelect"
    >
      <template #prepend-item>
        <v-list-item
          ripple
          @click="toggle"
        >
          <v-list-item-action>
            <v-icon :color="e11.length > 0 ? 'indigo darken-4' : ''">
              <v-icon>
                {{ mdi-checkbox-blank-outline }}
              </v-icon>
            </v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>
              Select All
            </v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-divider class="mt-2" />
      </template>

      <template #selection="{ index }">
        <span v-if="index === 0">
          Status: {{ e11.length }}
        </span>
      </template>
    </v-select>
  </v-container>
</template>

<script lang="ts">
import { defineComponent } from '@nuxtjs/composition-api'

export default defineComponent({
  setup () {
    const processaSelect = () => {
      console.log('Rodou evento aqui')
    }

    function formata (data: any) {
      console.log('ITEM DATA: ', data)
      return `Status: ${data.item.name}`
    }

    return {
      processaSelect,
      formata
    }
  },
  data () {
    return {
      e11: [],
      people: [
        { name: 'Sandra Adams', group: 'Group 1' },
        { name: 'Ali Connors', group: 'Group 1' },
        { name: 'Trevor Hansen', group: 'Group 1' },
        { name: 'Tucker Smith', group: 'Group 1' }
      ]
    }
  }

})
</script>
