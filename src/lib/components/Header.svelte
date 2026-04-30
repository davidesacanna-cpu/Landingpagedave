<script>
	let { isMobile = false } = $props();

	const logoTrinity =
		'https://www.figma.com/api/mcp/asset/e567d39d-8b58-40ba-8a58-079fadb7e2da';
</script>

<style>
	.header-container {
		display: flex;
		align-items: center;
		justify-content: space-between;
		padding: 24px 80px;
		width: 100%;
		position: relative;
		z-index: 10;
	}

	.logo {
		height: 25px;
		width: 112px;
	}

	.nav-link {
		color: #fafafa;
		font-family: 'Helvetica Neue', sans-serif;
		font-size: 24px;
		font-weight: 500;
		text-decoration: none;
		cursor: pointer;
	}

	.nav-link:hover {
		opacity: 0.8;
	}

	@media (max-width: 1024px) {
		.header-container {
			padding: 24px 40px;
		}
	}

	@media (max-width: 768px) {
		.header-container {
			padding: 16px 24px;
		}

		.logo {
			height: 20px;
			width: 90px;
		}

		.nav-link {
			font-size: 16px;
		}
	}
</style>

<div class="header-container">
	<div class="logo">
		<img src={logoTrinity} alt="Trinity Logo" style="width: 100%; height: 100%; object-fit: cover;" />
	</div>
	<a href="#about" class="nav-link">About</a>
</div>
