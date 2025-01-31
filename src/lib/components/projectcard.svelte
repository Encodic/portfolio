<script lang="ts">
	let {
		Title,
		Description,
		Image,
		Alt,
		slug
	}: { Title: string; Description: string; Image: string; Alt: string; slug: string } = $props();
</script>

<a class="card" href={slug} id={slug}>
	<div class="card-inner">
		<img class="image" src={Image} alt={Alt} draggable="false" />
		<div class="text">
			<div class="title">
				{Title}
			</div>
			<div class="description">
				{Description}
			</div>
		</div>
	</div>
</a>

<style>
	.card {
		border-radius: 30px;
		border: 3px solid #e0e0e0;
		overflow: hidden;
		cursor: pointer;
		text-decoration: none;
		color: black;
		outline: black;
		outline-width: 30px;
		box-shadow:
			8px 8px 16px #cccccc,
			-8px -8px 16px #ffffff;

		@media (prefers-color-scheme: dark) {
			color: white;
			border: 3px solid #212121;
			box-shadow:
				8px 8px 16px #0a0a0a,
				-8px -8px 16px #1a1a1a;
		}
	}

	.card :hover .title {
		color: #E2BE73;
	}

	.card-inner {
		display: flex;
		overflow: hidden;
		border-radius: 0px;
		background-color: #e9e9e9;
		@media (prefers-color-scheme: dark){
			background-color: #1D2026;
		}
	}

	.image {
		aspect-ratio: 16 / 9;
		height: 150px;
		@media screen and (max-width: 650px) {
			width: 100%;
			object-fit: cover;

			filter: blur(3px);
			-webkit-filter: blur(3px);
			filter: brightness(50%);
		}
	}

	.text {
		display: flex;
		flex-direction: column;
		gap: 0.5rem;
		padding: 1rem;
		@media screen and (max-width: 650px) {
			position: absolute;
			color: white;
		}
	}

	.title {
		font-size: 24px;
		font-weight: 500;
	}
</style>
