<template>

</template>

<script>
  import { eventBus } from '../main';

  export default {
    created(){
      eventBus.$on('quoteListEdited')
    }
  }
</script>
