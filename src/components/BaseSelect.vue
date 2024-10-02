<template>

  <label v-if="label">{{ label }}</label>

  <!-- modelValue is the default name of the property that vue will look for when doublebinding through v-model to custome components-->
  <select :value="modelValue" class="field" 
    v-bind="{
    ...$attrs,
    onChange: ($event) => { $emit('update:modelValue', $event.target.value) }
  }">
    <option  v-for="option in options" :value="option" :key="option" :selected="option === modelValue">{{ option }}
    </option>
  </select>
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
    },
    options: {
      type: Array,
      required: true
    }
  }
}

</script>