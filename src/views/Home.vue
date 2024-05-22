<template>
  <main class="p-4">
    <div
      class="mx-auto mt-4 grid max-w-6xl gap-4 md:grid-cols-2 lg:grid-cols-3"
    >
      <Card
        v-for="card in cards"
        :key="card.id"
        :id="card.id"
        :topic="card.topic"
        :title="card.title"
        :description="card.description"
        :author="card.author"
        :date="card.date"
      />
    </div>
  </main>
</template>

<script>
import Card from "@/components/Card.vue";
import CardsData from "@/data/cards.json";

export default {
  name: "Home",
  components: {
    Card,
  },
  data: () => ({
    cards: CardsData.data,
  }),
};
</script>
