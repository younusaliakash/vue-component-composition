<script setup>
import { ref } from "vue";

defineProps(["message"]);
defineEmits(["messageEmitted"]);

const newMessage = ref("Hello From Child");
</script>
<template>
  <div class="border-dashed border-2 border-indigo-600 p-5 rounded-lg mt-3">
    <h2>
      ChildComponent :
      <span class="text-indigo-600 font-bold">{{ message }} </span>
    </h2>
    <label
      class="block text-gray-700 text-sm font-bold mb-3 mt-3"
      for="customMessage"
    >
      Custom Message :
    </label>
    <input
      class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline mb-3"
      placeholder="Message Type Here..."
      id="customMessage"
      type="text"
      v-model="newMessage"
    />
    <button
      class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline mt-3"
      type="button"
      @click="$emit('messageEmitted', newMessage)"
    >
      Emit Message
    </button>
  </div>
</template>
