<script>
	import Coin from './Coin.svelte';

	let standings = [
		{ name: "kev002", price: "100", coin: "gold" },
		{ name: "Bigmangundy", price: "8", coin: "bronze" },
		{ name: "Bigmangundy", price: "8", coin: "silver" },
		{ name: "Hidden", price: "3", coin: "bronze" },
		{ name: "kev002", price: "200", coin: "gold" },
		{ name: "kev002", price: "100", coin: "gold" },
		{ name: "Bigmangundy Bigmangundy Bigmangundy Bigmangundy", price: "8", coin: "bronze" },
		{ name: "Bigmangundy", price: "8", coin: "silver" },
		{ name: "Hidden", price: "3", coin: "bronze" },
		{ name: "kev002", price: "200", coin: "gold" },
		{ name: "kev002", price: "100", coin: "gold" },
		{ name: "Bigmangundy", price: "8", coin: "bronze" },
		{ name: "Bigmangundy", price: "8", coin: "silver" },
		{ name: "Hidden", price: "3", coin: "bronze" },
		{ name: "kev002", price: "200", coin: "gold" },
		{ name: "kev002", price: "100", coin: "gold" },
		{ name: "Bigmangundy", price: "8", coin: "bronze" },
		{ name: "Bigmangundy", price: "8", coin: "silver" },
		{ name: "Hidden", price: "3", coin: "bronze" },
		{ name: "kev002", price: "200", coin: "gold" },
	];
</script>

<style>
	.standings{
		background: #222341;
		height: 420px;
		border-radius: 4px;
		box-shadow: 0px 8px 10px rgba(0, 0, 0, 0.14), 0px 3px 14px rgba(0, 0, 0, 0.12), 0px 4px 5px rgba(0, 0, 0, 0.2);
		padding: 16px;
		box-sizing: border-box;
		overflow: hidden;
	}
	.standings__wrapper{
		height: 100%;
		overflow: hidden;
	}
	.standings__list{
		margin: 0;
		padding: 0 30px 0 0;
		width: 100%;
		height: 100%;
		overflow-x: hidden;
		overflow-y: scroll;
	}
	.standings__list::-webkit-scrollbar {
	    display: none;
	}
	.standings__item{
		width: 100%;
		display: flex;
		margin-top: 8px;
		align-items: center;
	}
	.standings__item:first-child{
		margin-top: 0;
	}
	.standings__name{
		flex: 1 1;
		overflow: hidden;
	}
	.standings__name-text{
		white-space: nowrap;
		text-overflow: ellipsis;
		overflow: hidden;
	}
	.standings__price{
		flex: 0 0;
		margin: 0 8px;
	}
	.standings__coin{
		flex: 0 0;
	}
	@media (max-width: 767px) {
		.standings{
			background: none;
			box-shadow: none;
			padding: 0;
			font-size: 9px;
			height: 100%;
		}
		.standings__item{
			margin-top: 4px;
		}
	}
</style>

<div class="standings">
	<div class="standings__wrapper">
		<ul class="standings__list">
			{#each standings as { name, price, coin }}
				<li class="standings__item">
					<div class="standings__name">
						<div class="standings__name-text">{name}</div>
					</div>
					<div class="standings__price">${price}</div>
					<div class="standings__coin">
						<Coin size="small" color="{coin}" />
					</div>
				</li>
			{/each}
		</ul>
	</div>
</div>