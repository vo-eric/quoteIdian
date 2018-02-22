<template>
    <div class="container">
      <app-new-quote @quoteAdded="newQuote"></app-new-quote>
      <app-quote-view :quotes="quotes" @quoteRemoved="removeQuote"></app-quote-view>
      <div class="row">
        <div class="col-sm-12 text-center">
          <div class="alert alert-info">
            Click on a quote to delete it
          </div>
        </div>
      </div>
    </div>
</template>

<script>
  import QuoteView from './components/Quoteview.vue';
  import NewQuote from './components/NewQuote.vue'

  export default {
    data: function() {
      return {
        quotes: [
            'Here\'s a placeholder quote'
        ],
        maxQuotes: 10
      }
    },
    methods: {
      newQuote(quote) {
        this.quotes.push(quote);
      },
      removeQuote(index) {
        this.quotes.splice(index, 1);
      }
    },
    components: {
      appQuoteView: QuoteView,
      appNewQuote: NewQuote
    }
  }
</script>

<style>
</style>
