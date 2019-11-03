<template>
  <div class="row">
    <form action>
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
        <label for="quote">Quote</label>
        <textarea name="quote" id="quote" cols="30" rows="10" class="form-control" v-model="quote"></textarea>
      </div>
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
        <button class="btn btn-secondary" @click.prevent="createNewQuote">Add Quote</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      quote: ''
    };
  },
  methods: {
    createNewQuote() {
      this.$emit('newQuote', this.quote);
      this.quote = '';
    }
  }
};
</script>