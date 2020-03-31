<script>
	import { createEventDispatcher } from "svelte";
	const dispatch = createEventDispatcher();

	// Props
	export let name;

	const removeName = () => dispatch("remove", name);
</script>

<div class="card mt-4">
	<div class="card-body">
		<p class="mb-0">
			<button class="btn btn-danger" on:click={removeName}>x</button>
			{name}
		</p>
	</div>
</div>
