<script setup>
import { ref } from "vue";
import ChildComponent from "./ChildComponent.vue";

const textMessage = ref("Hello From Parent");

function messageEmitted(message) {
  textMessage.value = message;
}
</script>
<template>
  <div class="mockup-browser border border-base-300">
    <div class="mockup-browser-toolbar">
      <div class="input border border-base-300">https://younusaliakash.com</div>
    </div>

    <div class="flex justify-center px-4 py-16 border-t border-base-300">
      <div>
        <h1>Welcome!</h1>
        <h2 class="mt-3">
          Parent Component :
          <span class="text-indigo-600 font-bold">{{ textMessage }}</span>
        </h2>
        <ChildComponent
          @messageEmitted="messageEmitted"
          :message="textMessage"
        />
      </div>
    </div>
  </div>
</template>
