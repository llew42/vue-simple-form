<template>
	<form @submit.prevent="submitData">
		<div>
			<label for="name">Name</label>
			<input type="text" v-model="enteredName" />
		</div>
		<div>
			<label for="email">Email</label>
			<input type="text" v-model="enteredEmail" />
		</div>
		<div>
			<label for="phone">Phone</label>
			<input type="text" v-model="enteredPhone" />
		</div>
		<div>
			<button>Add Contact</button>
		</div>
	</form>
</template>

<script>
export default {
	emits: ["add-contact"],
	data() {
		return {
			enteredName: "",
			enteredEmail: "",
			enteredPhone: "",
		};
	},
	methods: {
		submitData() {
			this.$emit(
				"add-contact",
				this.enteredName,
				this.enteredEmail,
				this.enteredPhone
			);
		},
	},
};
</script>
<style>
#app input {
	font: inherit;
	padding: 0.15rem;
}
#app label {
	font-weight: bold;
	margin-right: 1rem;
	width: 7rem;
	display: inline-block;
}
#app form div {
	margin: 1rem 0;
}
</style>
