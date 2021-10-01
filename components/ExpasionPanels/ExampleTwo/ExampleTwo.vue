<template>
  <div class="container">
    <v-expansion-panels accordion>
      <!-- Profile -->
      <v-expansion-panel>
        <v-expansion-panel-header>
          Permissões para o perfil
        </v-expansion-panel-header>
        <v-expansion-panel-content>
          <v-checkbox
            label="Selecionar tudo"
            @change="selectAllForProbile($event)"
          />
          <v-checkbox
            v-model="addSelectedProfile"
            label="Adicionar perfil"
          />
          <v-checkbox
            v-model="editSelectedProfile"
            label="Editar perfil"
          />
          <v-checkbox
            v-model="viewSelectedProfile"
            label="Visualizar perfil"
          />
        </v-expansion-panel-content>
      </v-expansion-panel>

      <!-- Marca -->
      <v-expansion-panel>
        <v-expansion-panel-header>
          Selecione as permissões para Marcas
        </v-expansion-panel-header>
        <v-expansion-panel-content>
          <v-checkbox
            label="Selecionar tudo"
            @change="selectAllForProbile($event)"
          />
          <v-checkbox
            v-model="addSelectedProfile"
            label="Adicionar perfil"
          />
          <v-checkbox
            v-model="editSelectedProfile"
            label="Editar perfil"
          />
          <v-checkbox
            v-model="viewSelectedProfile"
            label="Visualizar perfil"
          />
        </v-expansion-panel-content>
      </v-expansion-panel>

      <!-- Marca -->
      <v-expansion-panel>
        <v-expansion-panel-header>
          Selecione as permissões para Unidades
        </v-expansion-panel-header>
        <v-expansion-panel-content>
          <v-checkbox
            label="Selecionar tudo"
            @change="selectAllForUnits($event)"
          />
          <v-checkbox
            v-model="addSelectedUnits"
            label="Adicionar unidade"
          />
          <v-checkbox
            v-model="editSelectedUnits"
            label="Editar unidades"
          />
          <v-checkbox
            v-model="viewSelectedUnits"
            label="Visualizar unidades"
          />
        </v-expansion-panel-content>
      </v-expansion-panel>
    </v-expansion-panels>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from '@nuxtjs/composition-api'

export default defineComponent({

  setup () {
    const addSelectedProfile = ref(false)
    const editSelectedProfile = ref(false)
    const viewSelectedProfile = ref(false)

    const addSelectedUnits = ref(false)
    const editSelectedUnits = ref(false)
    const viewSelectedUnits = ref(false)

    const selectAllForProbile = ($event: any) => {
      if ($event) {
        addSelectedProfile.value = true
        editSelectedProfile.value = true
        viewSelectedProfile.value = true
      } else {
        addSelectedProfile.value = false
        editSelectedProfile.value = false
        viewSelectedProfile.value = false
      }
    }

    const selectAllForUnits = ($event: any) => {
      if ($event) {
        addSelectedUnits.value = true
        editSelectedUnits.value = true
        viewSelectedUnits.value = true
      } else {
        addSelectedUnits.value = false
        editSelectedUnits.value = false
        viewSelectedUnits.value = false
      }
    }

    return {
      // Dados
      addSelectedProfile,
      editSelectedProfile,
      viewSelectedProfile,

      addSelectedUnits,
      editSelectedUnits,
      viewSelectedUnits,

      // Eventos
      selectAllForProbile,
      selectAllForUnits
    }
  }
})
</script>

<style lang="scss" scoped>
  @import './style.scss';
</style>
