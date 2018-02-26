<template>
  <div class="add-quote">
    <h3>Quote</h3>
    <textarea name="name" rows="8" cols="110" v-model="currentQuote" @keyup.enter="submitQuote"></textarea>
    <p>{{ currentQuote }}</p>
  </div>
</template>

<script type="text/javascript">
  import { eventBus } from '../main';

  export default {
    data: function() {
      return {
        currentQuote: "",
        quoteList: []
      };
    },
    methods: {
      submitQuote(){
        this.quoteList.push(this.currentQuote);
        eventBus.$emit('quoteListEdited', this.quoteList);
        this.currentQuote = "";
      }
    }
  }
</script>

<style scoped>
</style>
