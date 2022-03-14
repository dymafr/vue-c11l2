<template>
  <input v-model="usernameValue" type="text" />
  <p v-if="usernameError">{{ usernameError }}</p>

  <pre>
    {{ usernameValue }}
  </pre>
</template>

<script setup lang="ts">
import { useField } from 'vee-validate';

function validateName(value: string): true | string {
  if (!value.length) {
    return 'Le champ est obligatoire';
  } else if (value.length < 3) {
    return 'Le champ est trop court';
  } else if (value.length > 10) {
    return 'Le champ est trop long';
  } else {
    return true;
  }
}

const { value: usernameValue, errorMessage: usernameError } = useField(
  'username',
  validateName
);
</script>

<style scoped lang="scss"></style>
