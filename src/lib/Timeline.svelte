<script>
	import { onMount } from 'svelte';

	// Define the timeline data with dates
	export let events = [
		{ date: '2020-01-01', title: 'Event 1', description: 'Description of event 1' },
		{ date: '2021-06-15', title: 'Event 2', description: 'Description of event 2' },
		{ date: '2022-12-30', title: 'Event 3', description: 'Description of event 3' },
		{ date: '2023-05-10', title: 'Event 4', description: 'Description of event 4' }
	];

	// Function to convert date string to a Date object
	function parseDate(dateStr) {
		return new Date(dateStr);
	}

	// Store the timeline's start and end dates
	let startDate;
	let endDate;

	// Calculate the scale for positioning events based on their date
	onMount(() => {
		startDate = new Date(Math.min(...events.map((e) => parseDate(e.date)).map((d) => d.getTime())));
		endDate = new Date(Math.max(...events.map((e) => parseDate(e.date)).map((d) => d.getTime())));
	});
</script>

<div class="timeline-container">
	<!-- Timeline Line -->
	<div class="timeline"></div>

	<!-- Events -->
	{#each events as event}
		{#if startDate && endDate}
			<div
				class="event"
				style="
          left: {((parseDate(event.date) - startDate) / (endDate - startDate)) * 100}%;
        "
			>
				<div class="date">{event.date}</div>
				<div class="title">{event.title}</div>
				<div class="description">{event.description}</div>
			</div>
		{/if}
	{/each}
</div>

<style>
	.timeline-container {
		position: relative;
		width: 100%;
		height: 150px;
		margin: 50px 0;
		overflow-x: auto; /* Make the timeline scrollable horizontally */
	}

	.timeline {
		position: absolute;
		width: 200%; /* This makes the timeline wider than the container */
		height: 4px;
		background-color: #3498db;
		top: 50%;
		transform: translateY(-50%);
	}

	.event {
		position: absolute;
		bottom: 20px;
		text-align: center;
		width: 100px;
		margin-left: -50px; /* Half the width of the event for centering */
		font-size: 0.8em;
	}

	.event .date {
		font-weight: bold;
	}

	.event .title {
		font-size: 0.9em;
		margin-top: 5px;
	}

	.event .description {
		font-size: 0.8em;
		color: #666;
	}

	/* Optional: Styling for the scrollable bar */
	.timeline-container::-webkit-scrollbar {
		height: 8px;
	}

	.timeline-container::-webkit-scrollbar-thumb {
		background-color: #3498db;
		border-radius: 10px;
	}

	.timeline-container::-webkit-scrollbar-track {
		background: #f1f1f1;
	}
</style>
