<template>
    <div class="container">
      <h1>Quotes Added</h1>
      <app-progress-bar></app-progress-bar>
      <add-new-quote></add-new-quote>
      <added-quotes></added-quotes>
    </div>
</template>

<script>
    import ProgressBar from './components/progressBar.vue';
    import AddNewQuote from './components/AddNewQuote.vue';
    import AddedQuotes from './components/AddedQuotes.vue';

    export default {
      components: {
        'app-progress-bar': ProgressBar,
        'add-new-quote': AddNewQuote,
        'added-quotes': AddedQuotes
      }
    }
</script>

<style>
</style>
