<script>
	// Image constants from Figma
	const imgLogoTrinity = 'https://www.figma.com/api/mcp/asset/f57eba69-07cc-4ec3-be13-5370b5e77784';
	const imgImage = 'https://www.figma.com/api/mcp/asset/8214cedb-a7bb-4b26-93cb-2e2bb34bb67e';
	const imgScrittaPortfolio2 = 'https://www.figma.com/api/mcp/asset/b9952946-e3a0-49a3-af6d-39e9d28fd806';
	const imgScrittaPortfolio3 = 'https://www.figma.com/api/mcp/asset/4504a97a-d604-42e8-b224-542c7c80f5ea';
	const imgPolitecnicoBianco = 'https://www.figma.com/api/mcp/asset/afa13c86-ccf4-4074-a24d-6fad3f6e20a4';
	const imgVector = 'https://www.figma.com/api/mcp/asset/84752874-4701-4474-9a0a-5c21ac8e3433';
	const imgLine = 'https://www.figma.com/api/mcp/asset/c0759c8f-5594-47cc-9ef9-d8cb85643fd1';

	// Portfolio images
	const portfolioImages = [
		{
			name: 'FIL ROUGE',
			year: '2026',
			img: 'https://www.figma.com/api/mcp/asset/b512c02b-4e1f-4eb3-ac9e-7e3930c35b55'
		},
		{
			name: 'THRILL',
			year: '2026',
			img: 'https://www.figma.com/api/mcp/asset/4ebe8bae-6145-4206-a3f0-d73a41950b10'
		},
		{
			name: 'WHISPER',
			year: '2026',
			img: 'https://www.figma.com/api/mcp/asset/df6b5cb9-c558-447e-94a0-f862fd8413ca'
		},
		{
			name: 'HOME',
			year: '2026',
			img: 'https://www.figma.com/api/mcp/asset/408add22-4bee-46b5-af2e-e884381e62d3'
		},
		{
			name: 'BLACK',
			year: '2026',
			img: 'https://www.figma.com/api/mcp/asset/fdc83339-1956-4308-94b2-9ad50883bad7'
		},
		{
			name: 'STUDIOS',
			year: '2026',
			img: 'https://www.figma.com/api/mcp/asset/0187cf39-0455-459c-ba37-8b25869ddf18'
		}
	];

	let selectedYear = '2026';
</script>

<div class="desktop-container">
	<!-- Browser UI -->
	<div class="browser-chrome">
		<div class="browser-toolbar">
			<div class="browser-controls"></div>
			<div class="browser-tabs">
				<div class="tab-active">Web Design DDC</div>
			</div>
			<div class="browser-url">webdesign.ddc</div>
		</div>
	</div>

	<!-- Hero Section -->
	<div class="hero-section">
		<div class="hero-background">
			<img src={imgImage} alt="Hero background" class="hero-image" />
		</div>

		<!-- Top Bar -->
		<div class="top-bar">
			<div class="logo-container">
				<img src={imgLogoTrinity} alt="Trinity Logo" class="logo" />
			</div>
			<nav class="nav-links">
				<a href="#about" class="nav-link">About</a>
			</nav>
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
			<h3>PROGETTO TRINITY</h3>
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
						<div class="card-arrow">
							<svg viewBox="0 0 24 24" width="24" height="24">
								<path d="M7 7h10v10" stroke="#fafafa" stroke-width="2" fill="none" />
								<path d="M17 7L7 17" stroke="#fafafa" stroke-width="2" fill="none" />
							</svg>
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
	.desktop-container {
		width: 100%;
		background-color: #0a0a0a;
		position: relative;
		min-height: 100vh;
	}

	/* Browser Chrome */
	.browser-chrome {
		width: 100%;
		background-color: #202124;
		border-bottom: 1px solid #4d4d4d;
		position: relative;
		z-index: 100;
	}

	.browser-toolbar {
		display: flex;
		align-items: center;
		padding: 8px 12px;
		gap: 10px;
		height: 42px;
		background-color: #202124;
	}

	.browser-controls {
		width: 52px;
		height: 12px;
		background-color: #35363a;
		border-radius: 4px;
	}

	.browser-tabs {
		flex: 1;
		padding-left: 60px;
		color: #fafafa;
		font-size: 12px;
		font-family: Roboto, sans-serif;
	}

	.browser-url {
		margin-left: auto;
		padding: 6px 10px;
		background-color: #35363a;
		border-radius: 4px;
		color: #fafafa;
		font-size: 12px;
		width: 300px;
		text-align: center;
	}

	/* Hero Section */
	.hero-section {
		position: relative;
		width: 100%;
		height: 752px;
		display: flex;
		flex-direction: column;
		overflow: hidden;
	}

	.hero-background {
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		height: 851px;
		opacity: 0.66;
		z-index: 1;
	}

	.hero-image {
		width: 100%;
		height: 100%;
		object-fit: cover;
	}

	.top-bar {
		position: relative;
		z-index: 10;
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding: 24px 80px;
		height: 73px;
		width: 100%;
	}

	.logo-container {
		height: 25px;
		width: 112px;
		flex-shrink: 0;
	}

	.logo {
		width: 100%;
		height: 100%;
		object-fit: contain;
	}

	.nav-links {
		display: flex;
		gap: 24px;
		align-items: center;
	}

	.nav-link {
		color: #fafafa;
		font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif;
		font-size: 24px;
		font-weight: 500;
		text-decoration: none;
		cursor: pointer;
		transition: opacity 0.3s ease;
	}

	.nav-link:hover {
		opacity: 0.8;
	}

	.hero-content {
		position: relative;
		z-index: 10;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 1;
		gap: 40px;
	}

	.scritta-portfolio-2 {
		width: 716px;
		height: 328px;
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
		padding: 0 80px;
		margin-top: 125px;
	}

	.section-title {
		position: relative;
		margin-bottom: 40px;
		display: flex;
		align-items: center;
		gap: 20px;
	}

	.title-line {
		height: 3px;
		background-color: #fafafa;
		flex: 0 0 883px;
	}

	.section-title h3 {
		font-family: 'Zalando Sans Expanded', sans-serif;
		font-size: 36px;
		font-weight: 800;
		margin: 0;
		color: #fafafa;
		white-space: nowrap;
		flex-shrink: 0;
	}

	/* Filters */
	.filters {
		display: flex;
		gap: 16px;
		margin-bottom: 60px;
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
		gap: 60px;
		margin-bottom: 120px;
	}

	.portfolio-card {
		background-color: #0a0a0a;
		border: 1px solid #1a1a1a;
		border-radius: 0;
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
		height: 794px;
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
		padding: 20px;
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

	.card-arrow {
		width: 24px;
		height: 24px;
		flex-shrink: 0;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.card-arrow svg {
		width: 100%;
		height: 100%;
	}

	/* Footer */
	.footer {
		position: relative;
		margin-top: 300px;
		padding: 80px;
		background-color: #0a0a0a;
	}

	.footer-content {
		display: flex;
		justify-content: space-between;
		align-items: flex-start;
		margin-bottom: 60px;
	}

	.footer-text {
		font-family: 'Zalando Sans Expanded', sans-serif;
		font-size: 24px;
		font-weight: 300;
		color: #fafafa;
		line-height: 1.6;
	}

	.footer-text p {
		margin: 0;
	}

	.footer-text p:first-child {
		margin-bottom: 20px;
	}

	.footer-logo {
		width: 158px;
		height: 62px;
	}

	.footer-logo img {
		width: 100%;
		height: 100%;
		object-fit: contain;
	}

	.scritta-portfolio-3 {
		position: absolute;
		bottom: -200px;
		left: -82px;
		width: 1609px;
		height: 1216px;
		opacity: 0.4;
		z-index: 1;
		pointer-events: none;
	}

	.scritta-portfolio-3 img {
		width: 100%;
		height: 100%;
		object-fit: cover;
	}

	@media (max-width: 1024px) {
		.desktop-container {
			display: none;
		}
	}
</style>
