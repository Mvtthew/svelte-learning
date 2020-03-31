<script>
	import { createEventDispatcher } from "svelte";
	const dispatch = createEventDispatcher();

	let name = "";

	const addName = () => {
		dispatch("addname", name);
		name = "";
	};
</script>

<div class="card mt-4">
	<div class="card-body">
		<div class="form-group">
			<input class="form-control" bind:value={name} />
		</div>
		<button class="btn btn-primary" on:click={addName}>Add name</button>
	</div>
</div>
