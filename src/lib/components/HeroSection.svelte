<script>
	const imgHero = 'https://www.figma.com/api/mcp/asset/b9bf9166-ff04-462b-9f85-8e1b7fb408cf';
	const imgScritta = 'https://www.figma.com/api/mcp/asset/70abb77a-c620-4c38-b81a-beb369962e47';

	let { variant = 'desktop' } = $props();
</script>

<style>
	.hero-container {
		position: relative;
		width: 100%;
		display: flex;
		align-items: center;
		justify-content: center;
		min-height: 600px;
		overflow: hidden;
	}

	.hero-background {
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		opacity: 0.66;
		object-fit: cover;
		z-index: 1;
	}

	.hero-title {
		position: absolute;
		text-align: center;
		z-index: 5;
		color: white;
		font-family: 'Zalando Sans Expanded', sans-serif;
		font-weight: 700;
		text-transform: uppercase;
	}

	/* Desktop */
	@media (min-width: 1025px) {
		.hero-container {
			min-height: 600px;
		}

		.hero-title {
			font-size: 72px;
			width: 600px;
			line-height: 1.2;
		}
	}

	/* Tablet */
	@media (min-width: 769px) and (max-width: 1024px) {
		.hero-container {
			min-height: 450px;
		}

		.hero-title {
			font-size: 48px;
			width: 400px;
		}
	}

	/* Mobile */
	@media (max-width: 768px) {
		.hero-container {
			min-height: 350px;
		}

		.hero-title {
			font-size: 36px;
			width: 300px;
		}
	}
</style>

<div class="hero-container">
	<img src={imgHero} alt="Hero Background" class="hero-background" />
	<div class="hero-title">
		<img src={imgScritta} alt="Davide Sacanna" style="width: 100%; height: auto;" />
	</div>
</div>