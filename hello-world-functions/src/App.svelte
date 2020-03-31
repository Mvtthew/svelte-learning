<script>
	import User from "./User.svelte";

	let name = "Dave";
	let nameChanged = false;
	let fullName;

	let user = {
		name: "Mateusz",
		email: "mateusz2345678@gmail.com"
	};

	//Update every update
	$: {
		fullName = name + " Dee";
		console.log("Name changed!");
	}

	const changeName = () => {
		name = "Tim";
		nameChanged = true;
	};
</script>

<main>
	{#if nameChanged}
		<p>Name was changed!</p>
	{:else}
		<p>Name is not changed!</p>
	{/if}

	<h2>Hello {name}!</h2>
	<p>(full name: {fullName})</p>
	<button on:click={changeName}>Change name</button>
	<hr />
	<h2>User</h2>
	<User {user} />
</main>
