<template>
  <div class="row">
    <template v-for="quote in quotes">
      <div class="col-xs-auto text-center">
        <div class="card" style="width: 18rem;">
          <div class="card-body">
            <p class="card-text">{{ quote }}</p>
          </div>
        </div>
      </div>
    </template>
  </div>
</template>

<script>
  import { eventBus } from '../main';

  export default {
    data: function(){
      return {
        quotes: []
      };
    },
    created(){
      eventBus.$on('quoteListEdited', (quoteList) => {
        this.quotes = quoteList;
        console.log("Added a quote")
      });
    }
  }
</script>

<style scoped>
  .quote-card {
    border: 2px solid black;
  }
</style>
