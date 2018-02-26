<template>
  <div class="progress">
    <div class="progress-bar" :style="{width: barWidth + '%'}">
      <p v-show="barWidth > 0">{{ quoteCounter }}/10</p>
    </div>
  </div>
</template>

<script>
  export default {
    data: function(){
      return {
        barWidth: 0,
        quoteCounter: 0
      };
    }
  }
</script>
