<template>
  <div class="container">
    <quoteStatus :quoteCount='quoteCount'></quoteStatus>
    <quoteAdd :addQuote='addQuote'></quoteAdd>
    <div class="show-component">
      <quoteShow v-if='quotes.length' 
                 v-for='(quote, index) in quotes'
                 :key='quote'>
        <div class='quote' @click='deleteQuote(index)'>{{quote}}</div>
      </quoteShow>
    </div>
    <div class="alert alert-info" role="info">Info: Click on a Quote to delete it.</div>
  </div>
</template>

<script>
  import Status from './components/Status';
  import Show from './components/Show';
  import Add from './components/Add';
  export default {
    data: function() {
      return {
        quoteCount: 0,
        quotes: []
      }
    },
    watch: {
      quotes() {
        this.quoteCount = this.quotes.length;
      }
    },
    methods: {
      addQuote(quoteTemp) {
        if(this.quoteCount >= 10 ) {
          alert('You excedded the number of quotes allowed');
        }else {
          this.quotes.push(quoteTemp);
        }
      },
      deleteQuote(quoteIndex) {
        this.quotes.splice(quoteIndex, 1);
      }
    },
    components: {
      quoteStatus: Status,
      quoteAdd: Add,
      quoteShow: Show
    }
  }
</script>

<style>
  .show-component {
    display: inline-grid;
    grid-template-columns: repeat(4, 1fr);
  }
</style>

