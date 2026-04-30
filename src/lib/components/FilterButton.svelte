<script>
	let { year = 2026, isSelected = false } = $props();
</script>

<style>
	.filter-button {
		padding: 8px 16px;
		border-radius: 999px;
		border: none;
		cursor: pointer;
		font-family: 'Zalando Sans Expanded', sans-serif;
		font-weight: 500;
		font-size: 24px;
		transition: all 0.3s ease;
	}

	.filter-button.selected {
		background-color: #8a38f5;
		color: #fafafa;
	}

	.filter-button.unselected {
		background-color: transparent;
		color: #fafafa;
		opacity: 0.7;
	}

	.filter-button:hover {
		opacity: 1;
	}

	@media (max-width: 768px) {
		.filter-button {
			font-size: 20px;
			padding: 8px 16px;
		}
	}
</style>

<button
	class="filter-button"
	class:selected={isSelected}
	class:unselected={!isSelected}
	onclick={() => {}}
>
	{year}
</button>