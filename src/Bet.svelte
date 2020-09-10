<script>
	import Coin from './Coin.svelte';
	let isActive = false;
</script>

<style>
	.bet{
		background: #222341;
		border-radius: 4px;
		padding: 16px;
		height: 420px;
		box-sizing: border-box;
		box-shadow: 0px 8px 10px rgba(0, 0, 0, 0.14), 0px 3px 14px rgba(0, 0, 0, 0.12), 0px 4px 5px rgba(0, 0, 0, 0.2);
	}
	.bet__title{
		padding-bottom: 4px;
		border-bottom: 1px solid #5D60A7;
		margin-bottom: 16px;
	}
	.bet__places{
		display: flex;
		margin-bottom: 12px;
	}
	.bet__place{
		flex: 1 1;
		margin-left: 8px;
		text-align: center;
		background: #646673;
		border-radius: 4px;
		padding: 16px 8px;
		border: none;
		color: #fff;
		font-size: 12px;
		cursor: pointer;
	}
	.bet__place:first-child{
		margin-left: 0
	}
	.bet__place_active{
		background: #5D60A7;
	}
	.bet__coin{
		display: block;
	}
	.bet__text{
		margin-top: 8px;
		display: block;
	}
	.bet__prices{
		display: flex;
		flex-wrap: wrap;
		margin: -4px;
	}
	.bet__prices > div{
		flex: 0 0 50%;
		box-sizing: border-box;
		padding: 4px;
	}
	.bet__price{
		display: block;
		width: 100%;
		margin: 0;
		text-align: center;
		background: #646673;
		border-radius: 4px;
		padding: 8px;
		border: none;
		color: #fff;
		font-size: 16px;
		line-height: 1.5;
		cursor: pointer;
	}
	.bet__price_active{
		background: #5D60A7;
	}
	.bet__rate{
		display: flex;
		margin-top: 8px;
		border: 1px solid #646673;
		border-radius: 4px;
		overflow: hidden;
	}
	.bet__rate_active{
		border-color: #5D60A7;
	}
	.bet__label{
		flex: 0 0;
		white-space: nowrap;
		align-self: center;
		font-size: 12px;
		padding-left: 16px;
	}
	.bet__input{
		margin: 0;
		flex: 1 1;
		width: 100%;
		border-radius: 0;
		background: none;
		border: none;
		text-align: right;
		padding: 8px 16px;
		font-size: 16px;
		line-height: 1.5;
		font-weight: bold;
		outline: none;
		color: #5D60A7;
	}
	.bet__button{
		margin: 0;
		flex: 0 0 80px;
		border-radius: 0;
		background: #646673;
		border: none;
		color: #fff;
		font-size: 16px;
		line-height: 1.5;
		cursor: pointer;
	}
	.bet__rate_active .bet__button{
		display: none;
	}
	@media (max-width: 767px) {
		.bet{
			background: none;
			box-shadow: none;
			padding: 0;
			height: auto;
		}
		.bet__title{
			display: none;
		}
		.bet__button{
			flex: 0 0 30px;
			font-size: 14px;
		}
		.bet__input{
			font-size: 14px;
			padding: 8px;
		}
		.bet__label{
			padding-left: 8px;
			font-size: 9px;
		}
	}
</style>

<div class="bet">
	<div class="bet__title">Bet amount</div>
	<div class="bet__places">
		<button class="bet__place">
			<span class="bet__coin">
				<Coin size="middle" color="bronze" />
			</span>
			<span class="bet__text">x2</span>
		</button>
		<button class="bet__place bet__place_active">
			<span class="bet__coin">
				<Coin size="middle" color="silver" />
			</span>
			<span class="bet__text">x2</span>
		</button>
		<button class="bet__place">
			<span class="bet__coin">
				<Coin size="middle" color="gold" />
			</span>
			<span class="bet__text">x14</span>
		</button>
	</div>
	<div class="bet__prices">
		<div><button class="bet__price">$1</button></div>
		<div><button class="bet__price">$2</button></div>
		<div><button class="bet__price bet__price_active">$5</button></div>
		<div><button class="bet__price">$10</button></div>
		<div><button class="bet__price">$20</button></div>
		<div><button class="bet__price">$50</button></div>
		<div><button class="bet__price">$100</button></div>
		<div><button class="bet__price">$200</button></div>
	</div>
	<div class="bet__rate" class:bet__rate_active = {isActive}>
		<label class="bet__label" for="rate">Own rate:</label>
		<input type="text" id="rate" class="bet__input" placeholder="00.00$" disabled={isActive} />
		<button type="submit" class="bet__button" on:click="{() => isActive = true}">Ok</button>
	</div>
</div>