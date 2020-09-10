<script>
	let wagers = [
		{ time: "6:28", wager: "20.00", mult: "0.51", payout: "7.30"},
		{ time: "6:28", wager: "20.00", mult: "0.51", payout: "7.30"},
		{ time: "6:28", wager: "20.00", mult: "0.51", payout: "7.30"},
		{ time: "6:28", wager: "20.00", mult: "0.51", payout: "7.30"},
		{ time: "6:28", wager: "20.00", mult: "0.51", payout: "7.30"},
		{ time: "6:28", wager: "20.00", mult: "0.51", payout: "7.30"},
		{ time: "6:28", wager: "20.00", mult: "0.51", payout: "7.30"},
		{ time: "6:28", wager: "20.00", mult: "0.51", payout: "7.30"},
		{ time: "6:28", wager: "20.00", mult: "0.51", payout: "7.30"},
		{ time: "6:28", wager: "20.00", mult: "0.51", payout: "7.30"},
	]
</script>

<style>
	.wagers{
		padding-top: 36px;
		height: 100%;
		box-sizing: border-box;
		display: flex;
		flex-direction: column;
	}
	.wagers__title{
		padding-bottom: 4px;
		border-bottom: 1px solid #5D60A7;
		margin-bottom: 16px;
		flex: 0 0;
	}
	.wagers__table{
		flex: 1 1;
		overflow: hidden;
		display: flex;
		flex-direction: column;
	}
	.wagers__wrapper{
		height: 100%;
		width: 100%;
		overflow-x: hidden;
		overflow-y: scroll;
		padding-right: 30px;
		flex: 1 1;
	}
	.wagers__wrapper::-webkit-scrollbar {
	    display: none;
	}
	.wagers__header{
		flex: 0 0;
	}
	.wagers__header,
	.wagers__item{
		display: flex;
	}
	.wagers__header{
		background: #8D9BF3;
		border-radius: 2px;
		color: #2F3158;
		font-size: 12px;
		font-weight: 500;
		text-transform: uppercase;
	}
	.wagers__item{
		border-bottom: 1px solid #222341;
	}
	.wagers__time,
	.wagers__wager,
	.wagers__mult,
	.wagers__payout{
		flex: 1 1;
		padding: 8px 16px;
	}
	.wagers__wager,
	.wagers__mult,
	.wagers__payout{
		text-align: right;
	}
	@media (max-width: 767px) {
		.wagers{
			padding: 0;
		}
		.wagers__title{
			font-size: 14px;
			margin-bottom: 8px;
		}
		.wagers__mult{
			display: none;
		}
		.wagers__time,
		.wagers__wager,
		.wagers__payout{
			padding: 4px;
			line-height: 16px
		}
		.wagers__wager,
		.wagers__payout{
			font-size: 14px;
		}
		.wagers__time,
		.wagers__header .wagers__wager,
		.wagers__header .wagers__payout{
			font-size: 9px;
		}
	}
</style>

<div class="wagers">
	<div class="wagers__title">My wagers</div>
	<div class="wagers__table">
		<div class="wagers__header">
			<div class="wagers__time">Time</div>
			<div class="wagers__wager">Wager</div>
			<div class="wagers__mult">Mult</div>
			<div class="wagers__payout">Payout</div>
		</div>
		
		<div class="wagers__wrapper">
			{#each wagers as { time, wager, mult, payout }}
				<div class="wagers__item">
					<div class="wagers__time">{time}</div>
					<div class="wagers__wager">${wager}</div>
					<div class="wagers__mult">{mult}x</div>
					<div class="wagers__payout">${payout}</div>
				</div>
			{/each}
		</div>
	</div>
</div>