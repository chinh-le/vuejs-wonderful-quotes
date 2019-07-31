<template>
  <div class="container">
    <!-- <app-new-quote @quoteAdded="newQuote($event)"></app-new-quote> -->
    <!-- OR implicitly -->
    <app-new-quote @quoteAdded="newQuote"></app-new-quote>
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
  methods: {
    newQuote(quote) {
      this.quotes.push(quote);
    }
  },
  components: {
    appNewQuote: NewQuote,
    appQuoteGrid: QuoteGrid
  }
};
</script>
<style>
</style>
