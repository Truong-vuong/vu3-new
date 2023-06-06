<script setup lang="ts" generic="T extends Payment, U extends boolean | string">
import type { User, Payment } from "@/types/person";
// const props = defineProps<{
//     isShow: U,
//     isActive: T[]
// }>();
// before
// const props = defineProps<{
//   user: User
//   bar?: number
// }>()
// interface Props  {
//     user: User
//     isShow?: boolean
// }
//const props = defineProps<User & { isShow?: boolean }>()
  const { msg = 'hello' } = defineProps(['msg'])
console.log(msg);
</script>

<template>
  <h2>props component</h2>
</template>
