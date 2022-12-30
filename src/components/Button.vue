<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <button class="btn" :style="{ background: color }" @click="onClick()">
    {{ title }}
  </button>
</template>

<script lang="ts">
export default {
  name: "ButtonItem",
  props: {
    title: String,
    color: String,
  },
  methods: {
    onClick() {
      console.log("clicked");
    },
  },
};
</script>
