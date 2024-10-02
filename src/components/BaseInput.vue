<template>
    <label>{{ label }}</label>
    <input :placeholder="label"
      v-bind="$attrs"
      :value="modelValue"
      class="field"
      @input="$emit('update:modelValue', $event.target.value)"
      >

</template>

<script>

export default {
  props: {
    label: {
      type: String,
      default: ''
    },
    modelValue: {
      type: [String, Number],
      default: ''
    }
  }
}

</script>
