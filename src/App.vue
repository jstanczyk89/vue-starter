<template>
<div>
	<h1>Witaj w systemie do zapisów na zajêcia</h1>
	<div v-if="isAuthenticated">
		Zalogowano jako {{email}} <a @click="logMeOut()">Wyloguj</a>
	</div>
	<div v-else>
		<login-form @login="logMeIn($event)"
		button-label="Wje¿d¿am"></login-form>
		<login-form @login="logMeIn($event)"
		button-label="Loguje siê"></login-form>
	</div>
</div>

</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";

export default {
	components: {LoginForm},
	data() {
		  return {
		    email: '',
		    isAuthenticated:false
		  };
		},
	methods:{
		  logMeIn(username) {
			  this.isAuthenticated= username;
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


