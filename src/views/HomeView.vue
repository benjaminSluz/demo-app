<template>
  <div class="home">
    <h1>Hallo Welt!</h1>
    <ul>
      <li v-for="item in items">{{ item }}</li>
    </ul>
    <input @keyup.enter="addItem" v-model="newItem" />
  </div>
</template>
<script>
import { ref } from "vue";
import HelloWorld from "@/components/HelloWorld.vue";
export default {
  name: "HomeView",
  setup: () => {
    const newItem = ref("");
    const items = ref(["Äpfel", "Birnen", "Banane"]);
    function addItem() {
      items.value.push(newItem.value);
    }
    return { newItem, items, addItem };
  },
  components: { HelloWorld },
};
</script>
<style>
* {
  color: red;
}
</style>