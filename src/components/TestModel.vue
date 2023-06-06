<!-- BEFORE -->
<!-- <script setup lang="ts">
const props = defineProps(["modelValue"]);
const emit = defineEmits(["update:modelValue"]);
console.log("model value", props.modelValue);

function onInput(e: any) {
  emit("update:modelValue", e.target.value);
}
</script>

<template>
  <h2>Test model component</h2>
  <input :value="modelValue" @input="onInput" />
</template> -->

<!-- AFTER -->
<script setup lang="ts">
const modelValue = defineModel()
console.log("model value",modelValue.value)

// default model (consumed via `v-model`)
//const modelValue = defineModel()
   // ^? Ref<any>
//modelValue.value = 10

//const modelValue = defineModel<string>()
   // ^? Ref<string | undefined>
//modelValue.value = "hello"

// default model with options, required removes possible undefined values
//const modelValue = defineModel<string>({ required: true })
   // ^? Ref<string>

// with specified name (consumed via `v-model:count`)
//const count = defineModel<number>('count')
//count.value++

// with specified name and default value
//const count = defineModel<number>('count', { default: 0 })

</script>

<template>
  <input v-model="modelValue" />
</template>
