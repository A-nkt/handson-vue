<script setup lang="ts">
import { ref } from "vue";

const msg = ref("まだです!")
const onEntryKey = ():void => {
  msg.value = "エンターキーが押されました"
}
const onRightButtonClick = ():void => {
  msg.value = "ボタンが右クリックされました"
}
const onShiftClick = ():void => {
  msg.value = "シフトを押しながらクリックされました"
}
</script>

<template>
  <p>{{ msg }}</p>
  <input type="text" v-on:keydown.enter="onEntryKey"><br>
  <button v-on:click.right="onRightButtonClick">右クリック</button><br>
  <button v-on:click.shift="onShigtClick">シフトを押しながらクリック</button><br>
</template>