<template>
  <div class="row">
    <!-- KIM: since app-quote tag is not appended to the DOM, hence it won't get reacted to the click event -->
    <!-- <app-quote v-for="(quote, index) in quotes" :key="index" @click="deleteQuote(index)">{{ quote }}</app-quote> -->
    <!-- KIM: adding the 'native' modifier allows non-appended tag (app-quote) but its template gets reacted to the click event -->
    <app-quote
      v-for="(quote, index) in quotes"
      :key="index"
      @click.native="deleteQuote(index)"
    >{{ quote }}</app-quote>
  </div>
</template>
<script>
import Quote from "./Quote.vue";
export default {
  props: {
    quotes: Array
  },
  methods: {
    deleteQuote(index) {
      this.$emit("quoteDeleted", index);
    }
  },
  components: {
    appQuote: Quote
  }
};
</script>
<style>
</style>
