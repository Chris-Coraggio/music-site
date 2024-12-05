<script>
	import Timeline from '$lib/Timeline.svelte'; // Import the Timeline component

	// Define some example timeline data (you can customize it)
	let timelineData = [
		{ year: '2020', title: 'Event 1', description: 'Description of event 1' },
		{ year: '2021', title: 'Event 2', description: 'Description of event 2' },
		{ year: '2022', title: 'Event 3', description: 'Description of event 3' },
		{ year: '2023', title: 'Event 4', description: 'Description of event 4' }
	];
</script>

<main>
	<Timeline {timelineData} />
	<div class="container">
		<!-- iFrame -->
		<div class="iframe-container">
			<iframe
				src="https://musescore.com/user/11786606/scores/10331635/embed"
				width="100%"
				height="100%"
			></iframe>
		</div>

		<!-- Text and Timeline -->
		<div class="text-container">
			<h1>My Timeline</h1>
			<p>Below is a simple timeline with events over the years.</p>

			<!-- Use the Timeline component -->
		</div>
	</div>
</main>

<style>
	/* General styles */
	body {
		font-family: Arial, sans-serif;
		margin: 0;
		padding: 0;
		box-sizing: border-box;
	}

	.container {
		display: flex;
		flex-wrap: wrap;
		height: 100vh;
	}

	.iframe-container {
		flex: 1;
		background-color: #f0f0f0;
	}

	.text-container {
		flex: 1;
		padding: 20px;
		background-color: #fff;
	}

	@media (max-width: 768px) {
		.container {
			flex-direction: column; /* Stack the items vertically on mobile */
		}

		.iframe-container {
			height: 50vh; /* Make iframe take up half of the screen */
		}

		.text-container {
			padding-top: 20px;
		}
	}
</style>
