<script>
	// You can add any dynamic script or imports here if needed
</script>

<main>
	<div class="container">
		<!-- iFrame on the left for desktop, full screen for mobile -->
		<div class="iframe-container">
			<iframe
				src="https://musescore.com/user/11786606/scores/10331635/embed"
				width="100%"
				height="100%"
			></iframe>
		</div>

		<!-- Lorem Ipsum text on the right for desktop, below iframe on mobile -->
		<div class="text-container">
			<h1>Lorem Ipsum</h1>
			<p>
				Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed euismod, urna eu tincidunt
				congue, nisi est lacinia arcu, nec facilisis nulla odio nec quam. Vivamus vulputate
				tincidunt magna et volutpat. Etiam auctor risus ut velit hendrerit cursus. In sit amet
				placerat sapien.
			</p>
			<p>
				Morbi mollis lorem a lectus fermentum, in tincidunt augue varius. Aenean lobortis vehicula
				velit et tristique. Proin auctor libero eu lorem lacinia, et faucibus lorem rhoncus. Quisque
				tristique est turpis, ut sollicitudin sem placerat vel.
			</p>
			<p>
				Phasellus ultricies sapien ac eros suscipit, sed bibendum lorem volutpat. Mauris aliquam,
				orci at porttitor condimentum, orci justo interdum eros, eget cursus arcu lorem eget enim.
			</p>
		</div>
	</div>
</main>

<style>
	/* Basic styles */
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

	/* iFrame and text styling */
	iframe {
		border: none;
	}

	.iframe-container {
		flex: 1;
		height: 100vh;
		background-color: #f0f0f0;
	}

	.text-container {
		flex: 1;
		padding: 20px;
		overflow-y: auto;
		background-color: #fff;
	}

	.text-container p {
		line-height: 1.6;
	}

	/* Layout for larger screens (desktop) */
	@media (min-width: 768px) {
		.iframe-container {
			width: 50%; /* Left half for iframe */
		}

		.text-container {
			width: 50%; /* Right half for text */
		}
	}

	/* Layout for mobile screens */
	@media (max-width: 767px) {
		.iframe-container {
			width: 100%; /* Full width iframe */
			height: 50vh; /* iframe takes up half the screen height */
		}

		.text-container {
			width: 100%; /* Text takes up full width */
			padding-top: 20px; /* Space between iframe and text */
		}
	}
</style>
