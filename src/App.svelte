<script>
	let funny = false;
	let funnyButton = 0;

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
	<h1>It is currently not 7:27 PM :(</h1>
	<h3>Click this button in the meantime <strong>(O̯͓ͣ͂͟r̻̋̂ͬ͋ͧ ͓̻ͫͬ͐͛̀e̬̪̞͍̬͙͖ͪ̓̉̍̐̀ͨ̕l̪̮̺̰̬̤̪ͩ̋͑̋ͫ̇s̻͑̌̀̍̚͜e͔̞̫͍͟.͓̜̣̦̲̺ͩ̌̈.̼̗̓ͯ̓̂̑̃͢.̼͑̽̃͒̉̑̿̀)</strong></h3>
	<button on:click={() => funnyButton++}>funny button {funnyButton}</button>
	{#if funny}
		<video src="armstrong.webm" autoplay muted={!funnyButton >= 1 || null}>
			<track kind="captions">
		</video>
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

	video {
		max-width: 95vw;
		position: absolute;
		top: 50%;
		left: 50%;
		transform: translate(-50%, -50%);
	}

	strong {
		color: rgb(179, 0, 0);
	}

	@media (max-width: 600px) {
		h1 {
			font-size: 1.5rem;
		}
	}
</style>