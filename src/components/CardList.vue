<script>
import CardApp from "./CardApp.vue";
import { store } from "../store";

export default {
  data() {
    return {
      store,
    };
  },
  components: {
    CardApp,
  },
};
</script>

<template>
  <select v-model="store.arrselect" class="button-card" placeholder="Seleziona">
    <option v-for="option in store.arrselect" class="option-card">
      {{ option.archetype_name }}
    </option>
  </select>
  <button class=""></button>
  <div class="sfondo">
    <div class="cards-container">
      <CardApp
        v-for="(card, index) in store.cardList"
        :key="index"
        class="card-character"
        :card="card"
      />
    </div>
  </div>
</template>

<style lang="scss" scoped>
.sfondo {
  background-color: rgb(212, 143, 56);
  padding: 1.5rem;
}
.cards-container {
  display: flex;
  flex-wrap: wrap;
  max-width: 1100px;
  margin: auto;
}

.card-character {
  flex: 0 0 25%;
}
</style>
