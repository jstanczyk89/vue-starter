<template>
<div>
	<label>Zaloguj siê e-mailem</label> <input type="email" v-model="email">
	<button @click="enter()">Wchodzê</button>
</div>
</template>

<script>
export default {
props: ['buttonLabel'],
 data() {
     return {
         email: ''
     }
 },
 methods: {
     enter() {
         this.$emit('login', this.email);
     }
 }
}
</script>
