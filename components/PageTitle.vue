<template>
<div
    :class="`headline font-weight bold`"
    :style="`text-align: center; margin: 3em auto 2em; ${upperCase ? 'text-transform: uppercase;' : ''}`"
    >
    <div>{{ titleText }}</div>
  <div style="transform: translateY(-10px);">
    <u>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</u>
  </div>
  <div class="subheading" v-if="subText">
    {{ subText }}
  </div>
  </div>
</template>

<script>
  export default {
    props: {
      titleText: String,
      subText: String,
      upperCase: Boolean,
    }
  }
</script>