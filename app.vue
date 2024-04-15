<!-- <template>
  <div>
    <h1>Start Projet ! ! !</h1>
    <DataTable/>
  </div>
</template> -->
<template>
  <NuxtLayout>
    <v-app>
      <!-- <NuxtPage /> -->
      <DataTable/>
    </v-app>
  </NuxtLayout>
</template>

<script>
import DataTable from './components/DataTable.vue'

export default {
  name: 'App',
  component: {
    DataTable
  }
}
</script>