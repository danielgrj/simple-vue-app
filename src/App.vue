<template>
  <div class="container">
    <app-header :maxQuotes="maxQuotes" :quoteCount="quotes.length" />
    <quote-form @newQuote="handleNewQuote" />
    <quotes-grid :quotes="quotes" @deleteQuote="handleDeleteQuote" />
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">Info: Click on a Quote to delete it!</div>
      </div>
    </div>
  </div>
</template>

<script>
import Header from './components/Header';
import QuotesGrid from './components/QuotesGrid';
import QuoteForm from './components/QuoteForm';

export default {
  data: function() {
    return {
      quotes: ['Some quote'],
      maxQuotes: 10
    };
  },
  components: {
    appHeader: Header,
    quotesGrid: QuotesGrid,
    quoteForm: QuoteForm
  },
  methods: {
    handleNewQuote(quote) {
      if (this.quotes.length < this.maxQuotes) return this.quotes.push(quote);
      alert('Please delete a quote first!');
    },
    handleDeleteQuote(index) {
      console.log('handler');
      this.quotes.splice(index, 1);
    }
  }
};
</script>

<style>
</style>
