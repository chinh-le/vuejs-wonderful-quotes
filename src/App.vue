<template>
  <div class="container">
    <app-new-quote></app-new-quote>
    <app-quote-grid :quotes="quotes"></app-quote-grid>
  </div>
</template>
<script>
import NewQuote from "./components/NewQuote.vue";
import QuoteGrid from "./components/QuoteGrid.vue";
export default {
  data: function() {
    return {
      quotes: ["Just a Quote to see something", "Just another quote"],
      maxQuotes: 10
    };
  },
  components: {
    appNewQuote: NewQuote,
    appQuoteGrid: QuoteGrid
  }
};
</script>
<style>
</style>
