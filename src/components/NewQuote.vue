<template>
  <div class="row">
    <form action>
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 fomr-group">
        <label for="inputQuote">Quote</label>
        <textarea name id="inputQuote" rows="3" v-model="quote" class="form-control"></textarea>
      </div>
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 fomr-group">
        <!-- click.prevent: to not sending the form automatically as default form behavior -->
        <button @click.prevent="createNew" class="btn btn-primary">Add Quote</button>
      </div>
    </form>
  </div>
</template>
<script>
export default {
  data: function() {
    return {
      quote: ""
    };
  },
  methods: {
    createNew() {
      this.$emit("quoteAdded", this.quote);
      this.quote = "";
    }
  }
};
</script>
