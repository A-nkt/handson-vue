<script setup lang="ts">
import OneScreen from "./components/OneSection.vue"
</script>

<template>
  <h1>コンポーネント基礎</h1>
  <section>
    <h2>コンポーネント１個</h2>
    <OneScreen />
  </section>
  <section>
    <h2>コンポーネントが複数</h2>
    <OneScreen />
    <OneScreen />
    <OneScreen />
  </section>
</template>

<style>
section {
  border: blue 1px solid;
  margin: 10px;
}
</style>