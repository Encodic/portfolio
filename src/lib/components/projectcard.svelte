<script lang="ts">
	let {
		Title,
		Description,
		Skills,
		Image,
		Alt,
		slug,
		id
	}: { Title: string; Description: string; Skills: string; Image: string; Alt: string; slug: string; id: string; } = $props();
</script>

<a class="card" href={slug} id={id}>
	<div class="card-inner">
		<img class="image" src={Image} alt={Alt} draggable="false" />
		<div class="text">
			<div class="title">
				{Title}
			</div>
			<div class="description">
				{Description}
			</div>
			<div class="skills">
				{Skills}
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

	.card:hover {
		border: 3px solid #E2BE73;
	}

	.card:hover .title {
		color: #E2BE73;
	}

	.card-inner {
		display: flex;
		overflow: hidden;
		background-color: #f1f1f1;
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

	.skills {
		font-size: 12px;
		color:#8f8f8f;  
		display: flex;
		flex-direction: column;
		justify-content: flex-end;
		@media screen and (max-width: 650px) {
			font-size: 10px;
			color: #E2BE73;
			justify-content: flex-end;
		}
	}
</style>
