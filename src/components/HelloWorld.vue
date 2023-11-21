<script setup lang="ts">
import { ref, inject } from "vue";
const numberFromApp: number = inject("countNumber") ?? 0;
const messageText = ref(numberFromApp);

const plusPlus = () => {
  messageText.value++;
};

const minusMinus = () => {
  if (messageText.value > 0) {
    messageText.value--;
  }
};

const resettey = () => {
  messageText.value = 0;
};
</script>

<template>
  <h1>{{ messageText }}</h1>

  <div class="card">
    <button
      type="button"
      @click="
        (event) => {
          if (messageText > 0) {
            messageText = messageText - 1;
          }
        }
      "
    >
      Minus me!
    </button>
    <button type="button" @click="messageText = 0">Reset me!</button>
    <button type="button" @click="messageText = messageText + 1">
      Plus me!
    </button>
  </div>

  <div class="card">
    <button type="button" @click="minusMinus">
      Minus me but with a function!
    </button>
    <button type="button" @click="resettey">
      Reset me but with a function!
    </button>
    <button type="button" @click="plusPlus">
      Plus me but with a function!
    </button>
  </div>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
