<template>
<v-app>
  <ToolBar isFrontPage></ToolBar>
    <v-content>
      <nuxt />
    </v-content>
  </v-app>
</template>

<script>
import ToolBar from '~/components/ToolBar.vue'

export default {
  components: {
    ToolBar
  }}
</script>