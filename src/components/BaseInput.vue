<template>
  <label>{{ label }}</label>
  <input
    v-bind="{
      ...$attrs,
      onInput: event => $emit('update:modelValue', event.target.value)
    }"
    :value="modelValue"
  />
</template>

<script>
export default {
  props: {
    modelValue: {
      type: String,
      default: ''
    },
    label: {
      type: String,
      default: null
    }
  }
}
</script>

<style lang="scss" scoped></style>
