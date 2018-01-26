<template>
  <div class="col-xs-12">
  	<h2>Quotes Added</h2>
    <div class="progress">
		  <div class="progress-bar" role="progressbar" :aria-valuenow="quoteCount" aria-valuemin="0" aria-valuemax="10" :style="{width: quoteCount+'0%'}">
		    {{quoteCount}}/10
		  </div>
		</div>
  </div>
</template>

<script>
export default {
  props: ['quoteCount']
}
</script>

<style>

</style>
