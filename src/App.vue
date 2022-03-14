<template>
  <input v-model="usernameValue" type="text" />

  <pre>
    {{ usernameValue }}
  </pre>
</template>

<script setup lang="ts">
import { useField } from 'vue-validate';

const { value: usernameValue } = useField('username');
</script>

<style scoped lang="scss"></style>
