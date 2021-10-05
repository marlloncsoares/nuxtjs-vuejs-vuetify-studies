<template>
  <div>
    <SelectSlot />
  </div>
</template>

<script lang="ts">
import { defineComponent } from '@nuxtjs/composition-api'
import SelectSlot from '@/components/Selects/SelectSlot'

export default defineComponent({
  components: {
    SelectSlot
  },
  setup () {
    // console.log('Props: ', props)

  }
})
</script>

<style lang="scss" scoped>
.container {
  width: 100vw;
  height: 100vh;
  padding: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: tomato;
}
</style>
