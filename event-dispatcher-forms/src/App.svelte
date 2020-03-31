<script>
	import Name from "./Name.svelte";
	import NewName from "./NewName.svelte";

	let names = ["Dan", "Joe", "Danny", "Greg"];

	const removeName = e => {
		names = names.filter(name => name != e.detail);
	};
	const addName = e => {
		names = [e.detail, ...names];
	};
</script>

<div>
	<div class="container">
		<NewName on:addname={addName} />
		{#each names as name}
			<Name {name} on:remove={removeName} />
		{/each}
	</div>
</div>
