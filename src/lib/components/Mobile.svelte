<script>
	// Image constants from Figma
	const imgImage = 'https://www.figma.com/api/mcp/asset/7da4446f-50e9-4eb9-91bf-7a907e4d5b20';
	const imgScrittaPortfolio2 = 'https://www.figma.com/api/mcp/asset/446bf9ac-a167-44db-8f24-6c013db084f4';
	const imgScrittaPortfolio3 = 'https://www.figma.com/api/mcp/asset/534257f1-b3eb-4b20-99ef-4f9ed6de911d';
	const imgPolitecnicoBianco = 'https://www.figma.com/api/mcp/asset/e9a2b363-ae4e-4d1d-a8a6-2113fc69a116';
	const imgCellularConnection = 'https://www.figma.com/api/mcp/asset/2eb2fef2-9bcb-4562-99a5-da8912d8d406';
	const imgWifi = 'https://www.figma.com/api/mcp/asset/ae9bba1a-7831-4ece-8c2c-f9bd98e0ba48';
	const imgFrame = 'https://www.figma.com/api/mcp/asset/436e7b16-fdea-4943-93fe-2b582d8ef9ef';

	// Portfolio images
	const portfolioImages = [
		{
			name: 'FIL ROUGE',
			year: '2026',
			img: 'https://www.figma.com/api/mcp/asset/9e0fb44e-0d3a-47c3-a08e-15c6d0f8b7a2'
		},
		{
			name: 'THRILL',
			year: '2026',
			img: 'https://www.figma.com/api/mcp/asset/8f1c25b6-7e4a-4d2c-9f3a-1b8c5e6d7a9b'
		},
		{
			name: 'WHISPER',
			year: '2026',
			img: 'https://www.figma.com/api/mcp/asset/7c3e8f2d-6a1b-4c9e-8d2f-5a7b9c1e3f6d'
		},
		{
			name: 'HOME',
			year: '2026',
			img: 'https://www.figma.com/api/mcp/asset/6d4f9a1c-5b2e-4a8d-7f3e-4c6a8b2d5e9f'
		},
		{
			name: 'BLACK',
			year: '2026',
			img: 'https://www.figma.com/api/mcp/asset/5e5g0b2d-4c3f-3b9e-6e4f-3b5a7c1c4e8f'
		},
		{
			name: 'STUDIOS',
			year: '2026',
			img: 'https://www.figma.com/api/mcp/asset/4f6h1c3e-3d4g-2c0f-5d5g-2a4b6d0b3d7f'
		}
	];

	let selectedYear = '2026';
	let scrollY = 0;
</script>

<svelte:window bind:scrollY />

<div class="mobile-container">
	<!-- Status Bar -->
	<div class="status-bar">
		<span class="status-time">9:41</span>
		<div class="status-icons">
			<img src={imgCellularConnection} alt="cellular" class="icon" />
			<img src={imgWifi} alt="wifi" class="icon" />
			<img src={imgFrame} alt="battery" class="icon" />
		</div>
	</div>

	<!-- Hero Section -->
	<div class="hero-section">
		<div class="hero-background">
			<img src={imgImage} alt="Hero background" class="hero-image" />
		</div>

		<!-- Hero Title -->
		<div class="hero-content">
			<div class="scritta-portfolio-2">
				<img src={imgScrittaPortfolio2} alt="Portfolio text" />
			</div>
		</div>
	</div>

	<!-- Main Content -->
	<div class="main-content">
		<!-- Filters -->
		<div class="filters">
			<button class="filter-button active" on:click={() => (selectedYear = '2026')}>
				2026
			</button>
			<button class="filter-button" on:click={() => (selectedYear = '2025')}>
				2025
			</button>
		</div>

		<!-- Portfolio Grid -->
		<div class="portfolio-grid">
			{#each portfolioImages as project, idx (idx)}
				<div class="portfolio-card">
					<div class="card-image">
						<img src={project.img} alt={project.name} />
					</div>
					<div class="card-content">
						<div class="card-title">
							<span class="project-name">{project.name}</span>
							<span class="project-year">/ {project.year}</span>
						</div>
					</div>
				</div>
			{/each}
		</div>
	</div>

	<!-- Footer -->
	<div class="footer">
		<div class="footer-content">
			<div class="footer-text">
				<p>
					Based in Milan<br />
					Trinity Project
				</p>
				<p>
					Design, Creative Direction<br />© 2026 All rights reserved
				</p>
			</div>
		</div>
		<div class="footer-logo">
			<img src={imgPolitecnicoBianco} alt="Politecnico" />
		</div>
		<div class="scritta-portfolio-3">
			<img src={imgScrittaPortfolio3} alt="Portfolio footer text" />
		</div>
	</div>
</div>

<style>
	.mobile-container {
		width: 100%;
		max-width: 402px;
		background-color: #0a0a0a;
		position: relative;
		margin: 0 auto;
	}

	/* Status Bar */
	.status-bar {
		width: 100%;
		height: 48px;
		background-color: #0a0a0a;
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding: 12px 24px;
		font-family: 'SF Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
		border-bottom: 1px solid #1a1a1a;
		position: sticky;
		top: 0;
		z-index: 50;
	}

	.status-time {
		font-size: 16px;
		font-weight: 600;
		color: #fafafa;
	}

	.status-icons {
		display: flex;
		gap: 4px;
		align-items: center;
	}

	.icon {
		height: 12px;
		width: auto;
		object-fit: contain;
	}

	/* Hero Section */
	.hero-section {
		position: relative;
		width: 100%;
		height: 350px;
		display: flex;
		flex-direction: column;
		overflow: hidden;
	}

	.hero-background {
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		height: 603px;
		opacity: 0.66;
		z-index: 1;
	}

	.hero-image {
		width: 100%;
		height: 100%;
		object-fit: cover;
	}

	.hero-content {
		position: relative;
		z-index: 10;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 1;
		gap: 20px;
		padding-top: 40px;
	}

	.scritta-portfolio-2 {
		width: 192px;
		height: 88px;
		opacity: 0.9;
		z-index: 5;
	}

	.scritta-portfolio-2 img {
		width: 100%;
		height: 100%;
		object-fit: contain;
	}

	/* Main Content */
	.main-content {
		position: relative;
		z-index: 20;
		padding: 0 24px;
		margin-top: 80px;
	}

	/* Filters */
	.filters {
		display: flex;
		gap: 12px;
		margin-bottom: 40px;
		overflow-x: auto;
		padding-right: 24px;
	}

	.filter-button {
		padding: 8px 16px;
		border: none;
		border-radius: 999px;
		font-family: 'Zalando Sans Expanded', sans-serif;
		font-size: 20px;
		font-weight: 500;
		cursor: pointer;
		transition: all 0.3s ease;
		background-color: transparent;
		color: #fafafa;
		height: 45px;
		white-space: nowrap;
		flex-shrink: 0;
	}

	.filter-button.active {
		background-color: #8a38f5;
		color: #fafafa;
	}

	.filter-button:hover {
		opacity: 0.8;
	}

	/* Portfolio Grid */
	.portfolio-grid {
		display: grid;
		grid-template-columns: 1fr;
		gap: 30px;
		margin-bottom: 80px;
	}

	.portfolio-card {
		background-color: #0a0a0a;
		border: 1px solid #1a1a1a;
		overflow: hidden;
		transition: all 0.3s ease;
		cursor: pointer;
	}

	.portfolio-card:hover {
		border-color: #8a38f5;
		transform: translateY(-2px);
	}

	.card-image {
		width: 100%;
		height: 280px;
		overflow: hidden;
		background-color: #000;
	}

	.card-image img {
		width: 100%;
		height: 100%;
		object-fit: cover;
		transition: transform 0.3s ease;
	}

	.portfolio-card:hover .card-image img {
		transform: scale(1.02);
	}

	.card-content {
		padding: 12px;
		display: flex;
		justify-content: space-between;
		align-items: center;
		background-color: #0a0a0a;
	}

	.card-title {
		display: flex;
		gap: 6px;
		align-items: center;
		flex: 1;
		flex-wrap: wrap;
	}

	.project-name {
		font-family: 'Zalando Sans Expanded', sans-serif;
		font-size: 18px;
		font-weight: 500;
		color: #fafafa;
	}

	.project-year {
		font-family: 'Zalando Sans Expanded', sans-serif;
		font-size: 18px;
		font-weight: 500;
		color: #9499a0;
	}

	/* Footer */
	.footer {
		position: relative;
		padding: 40px 24px;
		background-color: #0a0a0a;
		margin-top: 100px;
	}

	.footer-content {
		margin-bottom: 30px;
	}

	.footer-text {
		font-family: 'Zalando Sans Expanded', sans-serif;
		font-size: 11px;
		font-weight: 300;
		color: #fafafa;
		line-height: 1.6;
		margin-bottom: 20px;
	}

	.footer-text p {
		margin: 0;
	}

	.footer-text p:first-child {
		margin-bottom: 10px;
	}

	.footer-logo {
		width: 61px;
		height: 24px;
		margin-bottom: 40px;
	}

	.footer-logo img {
		width: 100%;
		height: 100%;
		object-fit: contain;
	}

	.scritta-portfolio-3 {
		position: absolute;
		bottom: 20px;
		left: -172px;
		width: 725px;
		height: 564px;
		opacity: 0.2;
		z-index: 1;
		pointer-events: none;
	}

	.scritta-portfolio-3 img {
		width: 100%;
		height: 100%;
		object-fit: cover;
	}

	@media (min-width: 768px) {
		.mobile-container {
			display: none;
		}
	}
</style>
