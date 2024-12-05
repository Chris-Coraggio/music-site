<script>
	// The timeline points
	const timelinePoints = [
		{ id: 1, title: '2021', content: 'In 2021, major events took place...' },
		{ id: 2, title: '2022', content: 'In 2022, things changed significantly...' },
		{ id: 3, title: '2023', content: 'By 2023, the world had evolved...' },
		{ id: 4, title: '2024', content: "Now, in 2024, we're here!" }
	];

	// The currently selected tab
	let selectedTab = timelinePoints[0];
</script>

<div class="timeline-container">
	<div class="timeline">
		<!-- Line connecting the points -->
		<div class="timeline-line"></div>

		<!-- Render each point on the timeline -->
		{#each timelinePoints as point (point.id)}
			<div
				class="timeline-point {point.id === selectedTab.id ? 'selected' : ''}"
				on:click={() => {
					selectedTab = point;
				}}
			>
				{point.title}
			</div>
		{/each}
	</div>
</div>

<!-- Content below the timeline -->
<div class="content">
	<h2>{selectedTab.title}</h2>
	<p>{selectedTab.content}</p>
</div>

<style>
	/* Basic reset and styling */
	body {
		font-family: Arial, sans-serif;
		margin: 0;
		padding: 0;
	}

	.timeline-container {
		display: flex;
		justify-content: center;
		align-items: center;
		margin-top: 50px;
		position: relative;
	}

	.timeline {
		display: flex;
		justify-content: space-between;
		width: 80%;
		position: relative;
		height: 50px;
	}

	.timeline-point {
		width: 50px;
		height: 50px;
		border-radius: 50%;
		background-color: #ccc;
		display: flex;
		justify-content: center;
		align-items: center;
		cursor: pointer;
		transition:
			background-color 0.3s,
			transform 0.3s;
	}

	.timeline-point.selected {
		background-color: #4caf50;
		transform: scale(1.2);
	}

	.timeline-point:hover {
		background-color: #2196f3;
	}

	.timeline-line {
		position: absolute;
		top: 20px;
		width: 100%;
		height: 2px;
		background-color: #ccc;
	}

	.content {
		padding: 20px;
		text-align: center;
		background-color: #f4f4f4;
		margin-top: 30px;
	}

	.content h2 {
		margin-top: 0;
	}

	/* For smaller screens */
	@media (max-width: 600px) {
		.timeline {
			flex-direction: column;
			justify-content: flex-start;
			height: auto;
		}

		.timeline-container {
			margin-top: 20px;
		}
	}
</style>
