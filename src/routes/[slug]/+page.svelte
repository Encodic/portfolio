<script lang="ts">
	let { data }: any = $props();
	let Content = data.content;
</script>

<a class="back" href="/">Home</a>
<div class="about-wrapper">
	<article>
		<Content />
	</article>
</div>

<style>
	.about-wrapper {
		display: flex;
		flex-direction: column;
		width: min(100vw - 1.5rem, 840px);
		margin-inline: auto;
		margin-top: 10svh;
		margin-bottom: 15svh;
		justify-self: center;
		align-items: center;
	}

	.back {
		position: fixed;
		top: 10px;
		left: 10px;
		text-decoration: none;
		color: #E2BE73;
		padding: 5px 10px;
		border-radius: 10px;
		background-color: white;
		z-index: 2;
		border: 3px solid #e0e0e0;
			box-shadow:
				4px 4px 8px #cccccc,
				-4px -4px 8px #ffffff;
		@media (prefers-color-scheme: dark){
			background-color: #1D2026;
			border: 3px solid #212121;
			box-shadow:
				4px 4px 8px #0a0a0a,
				-4px -4px 8px #1a1a1a;
		}
	}

	.back:hover {
		border: 3px solid #E2BE73;
	}
</style>
