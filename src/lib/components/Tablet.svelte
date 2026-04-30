<script>
	// Image constants from Figma
	const imgImage = 'https://www.figma.com/api/mcp/asset/2282a04e-236f-4ae9-8ab1-f2e798c67d2f';
	const imgScrittaPortfolio2 = 'https://www.figma.com/api/mcp/asset/089009c9-6e6c-4238-8e2c-c060ae592d84';
	const imgScrittaPortfolio3 = 'https://www.figma.com/api/mcp/asset/83335c15-ba0c-4ab0-9f7b-7100e34ebac3';
	const imgPolitecnicoBianco = 'https://www.figma.com/api/mcp/asset/e3eb4e3b-e616-447e-8edb-82187db10ccb';
	const imgLine = 'https://www.figma.com/api/mcp/asset/f4b5f1e1-febe-4571-8f9b-9034a383b519';
	const imgCombinedShape = 'https://www.figma.com/api/mcp/asset/12471846-43a3-49b1-9ff3-f25826ccc084';
	const imgCombinedShape2 = 'https://www.figma.com/api/mcp/asset/97398cd3-734a-4f50-937c-3f60cce4b96b';
	const imgBatteryIcon = 'https://www.figma.com/api/mcp/asset/0896b43b-a448-4bfd-8e16-abb1b1e7bd8b';

	// Portfolio images
	const portfolioImages = [
		{
			name: 'FIL ROUGE',
			year: '2026',
			img: 'https://www.figma.com/api/mcp/asset/65e88ff1-2a0f-4794-9033-0eac89e674cf'
		},
		{
			name: 'THRILL',
			year: '2026',
			img: 'https://www.figma.com/api/mcp/asset/4d97192c-8ff2-4359-8aa3-0e4abd7858e1'
		},
		{
			name: 'WHISPER',
			year: '2026',
			img: 'https://www.figma.com/api/mcp/asset/49125fde-37dc-467d-af83-3b186730de32'
		},
		{
			name: 'HOME',
			year: '2026',
			img: 'https://www.figma.com/api/mcp/asset/95d4bee1-dda5-459b-bb25-1513321cfb80'
		},
		{
			name: 'BLACK',
			year: '2026',
			img: 'https://www.figma.com/api/mcp/asset/b1f843f7-7422-42b8-bb54-ad9638ba886f'
		},
		{
			name: 'STUDIOS',
			year: '2026',
			img: 'https://www.figma.com/api/mcp/asset/33d9af6c-17af-4bbb-aa95-fb332500778c'
		}
	];

	let selectedYear = '2026';
</script>

<div class="tablet-container">
	<!-- Status Bar -->
	<div class="status-bar">
		<div class="status-left">
			<span>9:41</span>
			<span>Tue Apr 1</span>
		</div>
		<div class="status-right">
			<span>📶 📡 100% 🔋</span>
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
		<!-- Section Title -->
		<div class="section-title">
			<div class="title-line"></div>
		</div>

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
			<div class="footer-logo">
				<img src={imgPolitecnicoBianco} alt="Politecnico" />
			</div>
		</div>
		<div class="scritta-portfolio-3">
			<img src={imgScrittaPortfolio3} alt="Portfolio footer text" />
		</div>
	</div>
</div>

<style>
	.tablet-container {
		width: 100%;
		background-color: #0a0a0a;
		position: relative;
		min-height: 100vh;
	}

	/* Status Bar */
	.status-bar {
		width: 100%;
		height: 32px;
		background-color: #0a0a0a;
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding: 4px 26px;
		font-family: 'SF Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
		font-size: 12px;
		color: #fafafa;
		border-bottom: 1px solid #1a1a1a;
	}

	.status-left {
		display: flex;
		gap: 8px;
		font-weight: 500;
	}

	.status-right {
		display: flex;
		gap: 4px;
		align-items: center;
	}

	/* Hero Section */
	.hero-section {
		position: relative;
		width: 100%;
		height: 400px;
		display: flex;
		flex-direction: column;
		overflow: hidden;
	}

	.hero-background {
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		height: 477px;
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
		gap: 30px;
	}

	.scritta-portfolio-2 {
		width: 374px;
		height: 171px;
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
		padding: 0 40px;
		margin-top: 80px;
	}

	.section-title {
		position: relative;
		margin-bottom: 40px;
		display: flex;
		align-items: center;
		gap: 20px;
	}

	.title-line {
		height: 2px;
		background-color: #fafafa;
		flex: 0 0 450px;
	}

	/* Filters */
	.filters {
		display: flex;
		gap: 16px;
		margin-bottom: 50px;
		flex-wrap: wrap;
	}

	.filter-button {
		padding: 8px 16px;
		border: none;
		border-radius: 999px;
		font-family: 'Zalando Sans Expanded', sans-serif;
		font-size: 24px;
		font-weight: 500;
		cursor: pointer;
		transition: all 0.3s ease;
		background-color: transparent;
		color: #fafafa;
		height: 45px;
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
		grid-template-columns: repeat(2, 1fr);
		gap: 40px;
		margin-bottom: 100px;
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
		transform: translateY(-4px);
	}

	.card-image {
		width: 100%;
		height: 397px;
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
		padding: 16px;
		display: flex;
		justify-content: space-between;
		align-items: center;
		background-color: #0a0a0a;
	}

	.card-title {
		display: flex;
		gap: 8px;
		align-items: center;
		flex: 1;
	}

	.project-name {
		font-family: 'Zalando Sans Expanded', sans-serif;
		font-size: 24px;
		font-weight: 500;
		color: #fafafa;
	}

	.project-year {
		font-family: 'Zalando Sans Expanded', sans-serif;
		font-size: 24px;
		font-weight: 500;
		color: #9499a0;
	}

	/* Footer */
	.footer {
		position: relative;
		margin-top: 200px;
		padding: 40px;
		background-color: #0a0a0a;
	}

	.footer-content {
		display: flex;
		justify-content: space-between;
		align-items: flex-start;
		margin-bottom: 40px;
	}

	.footer-text {
		font-family: 'Zalando Sans Expanded', sans-serif;
		font-size: 16px;
		font-weight: 300;
		color: #fafafa;
		line-height: 1.6;
	}

	.footer-text p {
		margin: 0;
	}

	.footer-text p:first-child {
		margin-bottom: 15px;
	}

	.footer-logo {
		width: 86px;
		height: 34px;
	}

	.footer-logo img {
		width: 100%;
		height: 100%;
		object-fit: contain;
	}

	.scritta-portfolio-3 {
		position: absolute;
		bottom: -100px;
		left: -37px;
		width: 818px;
		height: 628px;
		opacity: 0.3;
		z-index: 1;
		pointer-events: none;
	}

	.scritta-portfolio-3 img {
		width: 100%;
		height: 100%;
		object-fit: cover;
	}

	@media (max-width: 768px) {
		.tablet-container {
			display: none;
		}
	}

	@media (min-width: 1025px) {
		.tablet-container {
			display: none;
		}
	}
</style>
