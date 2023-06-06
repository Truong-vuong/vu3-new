<script setup lang="ts">
defineSlots<{
  default(props: { msg: string }): any // or VNode[]
}>();
</script>

<template>
    <h2>define Slot page</h2>
    <div>
        <p>title: this is Title</p>
        <slot :msg="'abc'"></slot>
    </div>
</template>