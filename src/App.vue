<template>
<div>
<h1>Witaj w systemie do zapisów na zajêcia</h1>
	<div v-if="isAuthenticated">
	Zalogowano jako {{email}}
	<a @click="logMeOut()">Wyloguj</a>
	</div>
	<div v-else>
		<label>Zaloguj siê emailem</label> 
		<input type="text" v-model="email">
		<button @click="logMeIn()">Wchodzê</button>
	</div>
</div>

</template>

<script>
export default {
	data() {
		  return {
		    email: '',
		    isAuthenticated:false
		  };
		},
	methods:{
		  logMeIn() {
			  this.isAuthenticated=true
			  },
		  logMeOut(){
			  this.isAuthenticated=false
			  this.email = ''
		  }
	},
	
}
</script>

<style>
</style>
