<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <transition
          appear
          enter-active-class="animated lightSpeedInRight"
          v-if="text"
        >
          <div class="text-h5 text-center full-width">{{ text }}</div>
        </transition>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script setup>
import { onMounted, ref } from "vue";

const text = ref("");
onMounted(() => {
  setTimeout(() => {
    text.value = "Welcome to Lunar Blessings";
  }, 500);
});
</script>
