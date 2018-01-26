<template>
	<div>
		<div class="row">
		  <div class="col-xs-6 col-xs-offset-2">
		    <h4>Quote</h4>
		    <textarea rows="4" cols="75" 
		    					v-model="quoteText"
		    					@keyup.enter='submitQuote()'>
				</textarea>
		  </div>
		</div>
		<button class='btn btn-primary' @click="submitQuote()">Add Quote</button>
	</div>
	
	
</template>

<script>
export default {
	props: {
		addQuote: Function
	},
  data() {
  	return {
  		quoteText: ''
  	}
  },
  methods: {
  	submitQuote() {
  		this.addQuote(this.quoteText);
  		this.quoteText='';
  		this.quoteText.focus;
  	}
  }
}
</script>

<style scoped="">
	button {
		display: block;
		margin: 10px auto;
	}
</style>
