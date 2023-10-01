<script setup lang="ts">
import { computed } from "vue"
import { useCounterStore } from "@/stores/counter"

const counterStore = useCounterStore()
const count = computed(
  () : number => {
    return counterStore.counter;
  }
);

const doubleCount = computed(
  (): number => {
    return counterStore.doubleCount
  }
)

const onIncrementClick = () => {
  counterStore.incrementCount()
}
</script>

<template>
    <p>現在のポイント : {{  count }}</p><br>
    <p>現在のポイントをさらに倍：{{ doubleCount }}</p><br>
    <button @click="onIncrementClick">加算</button>
</template>

<style scoped>
</style>
