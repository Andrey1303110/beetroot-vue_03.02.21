<template>
  <div id="app">

    <card v-for="card in cards" :key="card.title">
      <template #header>
        <h1>{{ card.title }}</h1>
      </template>
      <template #default>
        <p :style="`color: ${card.color}`">{{ card.text }}</p>
      </template>
    </card>

    <list>
      <template #listItem="listItem">
        <span style="color: blue">Item {{ listItem.counter }} / {{ listItem.counter1 }}</span>
      </template>
    </list>
    
  </div>
</template>

<script>
import Card from "./components/Card";
import List from "./components/List";

export default {
  components: {
    Card, List
  },
  data() {
    return {
      cards: [
        {
          title: "Card 1",
          text: "Text for the Card 1",
          color: "red",
        },
        {
          title: "Card 2",
          text: "Text for the Card 2",
          color: "green",
        },
        {
          title: "Card 3",
          text: "Text for the Card 3",
          color: "blue",
        }
      ]
    }
  },
}
</script>