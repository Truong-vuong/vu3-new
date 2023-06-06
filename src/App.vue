<script setup lang="ts">
import TestProps from './components/TestProps.vue';
import TestEmit from './components/TestEmit.vue';
import TestSlots from './components/TestSlots.vue';
import TestModel from './components/TestModel.vue';
import TestOptions from './components/TestOptions.vue';
import { type User } from './types/person';
import { ref } from 'vue';

const user: User = {
  name: "Vuong",
  age: 30,
  isMale: true,
};
const count = ref(1);
const increment = (a: any) => {
  count.value = count.value + a
}
const msg = "hello";

const modalVal = ref('')
const val = (e: any) => {
  console.log(e)
  modalVal.value = e;
}
</script>

<template>
  <div class="box">
    <h1>Hello</h1>
    <!-- <TestProps name="aaa" :age="30" :isMale="false" :isShow="true"></TestProps> -->
    <!-- <TestProps :isActive="[{name: 'a', price: 100 },{name: 'a', price: 100 }]" :isShow="true"></TestProps> -->
    <TestProps msg="sss"></TestProps>
    <TestEmit @increment="increment"></TestEmit>
    <p>{{ count }}</p>

    <TestSlots>
      <template v-slot="{ msg }">
        {{ msg }}
      </template>
    </TestSlots>

    <TestModel v-model="modalVal" @update:modelValue="val"></TestModel>
    <TestOptions></TestOptions>
  </div>
</template>

<style scoped>
.box {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>
