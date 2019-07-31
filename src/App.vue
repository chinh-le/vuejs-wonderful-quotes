<template>
  <div class="container">
    <app-quote-progress :quoteCount="quotes.length" :quoteMax="maxQuotes"></app-quote-progress>
    <!-- <app-new-quote @quoteAdded="newQuote($event)"></app-new-quote> -->
    <!-- OR implicitly -->
    <app-new-quote @quoteAdded="newQuote"></app-new-quote>
    <app-quote-grid :quotes="quotes" @quoteDeleted="removeQuote"></app-quote-grid>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">Info: Click on a Quote to delete it!</div>
      </div>
    </div>
  </div>
</template>
<script>
import QuoteProgress from "./components/QuoteProgress.vue";
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
      if (this.quotes.length >= this.maxQuotes) {
        return alert("Max quotes reached! Delete quote to add more...");
      }
      this.quotes.push(quote);
    },
    removeQuote(index) {
      this.quotes.splice(index, 1);
    }
  },
  components: {
    appQuoteProgress: QuoteProgress,
    appNewQuote: NewQuote,
    appQuoteGrid: QuoteGrid
  }
};
</script>
<style>
</style>
