<script lang="ts">
	import Arrow from '$lib/icons/corner-down-right.svelte';

	let {
		Title,
		Role,
		url,
		id,
		date,
		Description
	}: { Title: string; Role: string; url: string; id: string; date: string; Description: string } =
		$props();
</script>

<a class="card" href={url} {id}>
	<div class="arrow">
		<Arrow />
	</div>
	<div class="card-inner">
		<div>
			<div class="title">
				<div>
					{Title}
				</div>
				<div class="date">{date}</div>
			</div>
			<div class="role">
				{Role}
			</div>
			<hr color="#E2BE73"/>
		</div>
		<div class="description">
			{Description}
		</div>
	</div>
</a>

<style>
	a,
	a:visited,
	a:hover,
	a:active {
		color: inherit;
	}

	.card {
		display: flex;
		flex-direction: row;
		overflow: hidden;
		cursor: pointer;
		text-decoration: none;
	}

	.arrow {
		padding-left: 0;
		padding-right: 0.5rem;

		transition:
			padding-left 0.2s,
			padding-right 0.2s;
	}

	.card:hover .arrow {
		padding-left: 0.5rem;
		padding-right: 0;
		color: #E2BE73;
	}

	.card-inner {
		display: flex;
		flex-direction: column;
		overflow: hidden;
	}

	.title {
		display: flex;
		gap: 0.5rem;
		font-size: 24px;
		font-weight: 500;
	}

	.card:hover .title {
		color: #E2BE73;
	}

	.role {
		font-size: 16px;
		color: #404040;
		@media (prefers-color-scheme: dark) {
			color: #909090;
		}
	}

	.date {
		color: #707070;
		font-size: 14px;
	}

	.description {
		margin-top: 0.5rem;
		font-size: 1rem;
	}
</style>
