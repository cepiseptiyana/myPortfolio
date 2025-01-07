<script setup>
import navbar from "./components/header.vue";
import content1 from "./components/content1.vue";
import content2 from "./components/content2.vue";
import content3 from "./components/content3.vue";
import content4 from "./components/content4.vue";
</script>

<template>
  <header>
    <div class="wrapper">
      <navbar />
    </div>
  </header>

  <main>
    <content1 />
    <content2 />
    <content3 />
    <content4 />
  </main>
</template>

<style scoped></style>
