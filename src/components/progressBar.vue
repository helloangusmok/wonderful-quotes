<template>
  <div class="progress">
    <div class="progress-bar" :style="{width: barWidth + '%'}">
      <p v-show="barWidth > 0">{{ quoteCounter }}/10</p>
    </div>
  </div>
</template>

<script>
  import { eventBus } from '../main'

  export default {
    data: function(){
      return {
        quotes: []
      };
    },
    computed: {
      quoteCounter: function() {
        if(this.quotes){
          return this.quotes.length;
        } else {
          return 0;
        }
      },
      barWidth: function(){
        return this.quoteCounter * 10;
      }
    },
    created(){
      eventBus.$on('quoteListEdited', (quoteList) => {
        this.quotes = quoteList;
        console.log(this.quotes);
      });
    }
  }
</script>

<style scoped>
  .progress-bar {
    transition: width .7s;
  }
</style>
