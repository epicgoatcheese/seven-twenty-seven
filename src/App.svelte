<script>
	export let funny = false;

	const funnyTime = {
		hours: 19,
		minutes: 27,
	};

	setInterval(() => {
		const hours = new Date().getHours();
		const minutes = new Date().getMinutes();

		if (hours === funnyTime.hours && minutes === funnyTime.minutes) {
			funny = true;
		}
	}, 1000);
</script>

<div class="wrapper">
	{#if !funny}
		<h1>It is currently not 7:27 PM :(</h1>
		<h2>Come back at 7:27 PM</h2>
	{:else}
		<h1>It is currently 7:27 PM</h1>
		<iframe width="560" height="315" src="https://www.youtube.com/embed/dQw4w9WgXcQ?&autoplay=1" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
	{/if}
</div>

<style>
	.wrapper {
		height: 100vh;
		display: flex;
		justify-content: center;
		align-items: center;
		flex-direction: column;
	}
</style>