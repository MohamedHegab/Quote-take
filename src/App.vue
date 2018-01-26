<template>
  <div class="container">
    <quoteStatus></quoteStatus>
    
  </div>
</template>

<script>
  import Status from './components/Status';
  import Show from './components/Show';
  import Add from './components/Add';
  export default {
    components: {
      quoteStatus: Status,
      quoteAdd: Add,
      quoteShow: Show
    }
  }
</script>

<style>

</style>
