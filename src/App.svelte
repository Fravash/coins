<script>
	import Bet from './Bet.svelte';
	import Standings from './Standings.svelte';
	import Wagers from './Wagers.svelte';
	import Info from './Info.svelte';
</script>

<style>
	:global(html, body){
		margin: 0;
		padding: 0;
		font: 16px/1.5 Roboto, Ubuntu, "Helvetica Neue", "Segoe UI", sans-serif;
		background: #2F3158;
		color: #fff;
	}
	.layout{
		height: 100%;
		min-height: 840px;
		box-sizing: border-box;
		display: grid;
		width: 100%;
		padding: 50px;
		grid-template-columns: 25% auto 25%;
  		grid-template-rows: 420px auto;
  		grid-template-areas: "bet info standings" "wagers wagers wagers";
	}
	.layout__bet{
		grid-area: bet;
	}
	.layout__standings{
		grid-area: standings;
	}
	.layout__info{
		grid-area: info;
		overflow: hidden;
	}
	.layout__wagers{
		grid-area: wagers;
		overflow: hidden;
	}
	@media (max-width: 1279px) {
		.layout{
			min-height: 1120px;
			padding: 32px 0;
			grid-template-columns: 50% 50%;
	  		grid-template-rows: 395px 420px auto;
	  		grid-template-areas: "info info" "standings bet" "wagers wagers";
		}
		.layout__bet{
			margin: 0 24px 0 8px;
		}
		.layout__standings{
			margin: 0 8px 0 24px;
		}
		.layout__wagers{
			margin: 0 24px;
		}
	}
	@media (max-width: 767px) {
		.layout{
			min-width: 360px;
			min-height: 665px;
			padding: 0 0 24px;
			grid-template-rows: 300px 1fr 1fr;
			grid-template-areas: "info info" "standings bet" "wagers bet";
		}
		.layout__bet{
			margin: 0 16px 0 4px;
		}
		.layout__standings{
			margin: 0 4px 0 16px;
			overflow: hidden;
			padding-bottom: 10px;
		}
		.layout__wagers{
			margin: 0 4px 0 16px;
			overflow: hidden;
			padding-top: 10px;
		}
	}
</style>

<div class="layout">
	<div class="layout__bet">
		<Bet />
	</div>
	<div class="layout__info">
		<Info />
	</div>
	<div class="layout__standings">
		<Standings />
	</div>
	<div class="layout__wagers">
		<Wagers />
	</div>
</div>