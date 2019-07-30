<template>
  <div class="container">
    <app-quote-grid :quotes="quotes"></app-quote-grid>
  </div>
</template>
<script>
import QuoteGrid from "./components/QuoteGrid.vue";
export default {
  data: function() {
    return {
      quotes: ["Just a Quote to see something", "Just another quote"],
      maxQuotes: 10
    };
  },
  components: {
    appQuoteGrid: QuoteGrid
  }
};
</script>
<style>
</style>
