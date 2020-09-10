<script>
	import Coin from './Coin.svelte';
	import Modal from './Modal.svelte';

	let indexModal = 0;
	let showModal = false;

	function historyClick(e) {
		indexModal = e.target.closest("a").dataset.index;
		showModal = true;
	}

	let game = [ 
		{color: "bronze"},
		{color: "silver"}, 
		{color: "bronze"}, 
		{color: "gold"},
		{color: "silver"}, 
		{color: "bronze"}, 
		{color: "silver"}, 
		{color: "bronze"}, 
		{color: "silver"}, 
		{color: "bronze"},
		{color: "silver"}, 
		{color: "bronze"}, 
		{color: "silver"},
		{color: "bronze"}, 
		{color: "silver"}, 
		{color: "bronze"}, 
		{color: "silver"}, 
		{color: "bronze"},
		{color: "silver"}, 
		{color: "bronze"}, 
		{color: "silver"},
		{color: "bronze"}, 
		{color: "silver"}, 
		{color: "bronze"}, 
		{color: "silver"}, 
		{color: "bronze"},
		{color: "silver"}, 
		{color: "bronze"}, 
		{color: "silver"}
	];
	let explorer = [ 
		{
			color: "bronze",
			id: "4532c23kv54v5435vmn52klv2l5mv45l",
			started: "Wed, Sep 2, 2020 8:39 AM",
			bet: "9",
			hash: "nsdfjsdnjkfnssdfgheiushthfshfoaojriojfkrekoppofoewqfqwekeffmwqkfmkwqmfpwqffpqwmfmwqp"
		},
		{
			color: "silver",
			id: "4532c23kv54v5435vmn52klv2l5mv45l",
			started: "Wed, Sep 2, 2020 8:39 AM",
			bet: "8",
			hash: "nsdfjsdnjkfnssdfgheiushthfshfoaojriojfkrekoppofoewqfqwekeffmwqkfmkwqmfpwqffpqwmfmwqp"
		}, 
		{
			color: "bronze",
			id: "4532c23kv54v5435vmn52klv2l5mv45l",
			started: "Wed, Sep 2, 2020 8:39 AM",
			bet: "7",
			hash: "nsdfjsdnjkfnssdfgheiushthfshfoaojriojfkrekoppofoewqfqwekeffmwqkfmkwqmfpwqffpqwmfmwqp"
		}, 
		{
			color: "gold",
			id: "4532c23kv54v5435vmn52klv2l5mv45l",
			started: "Wed, Sep 2, 2020 8:39 AM",
			bet: "90",
			hash: "nsdfjsdnjkfnssdfgheiushthfshfoaojriojfkrekoppofoewqfqwekeffmwqkfmkwqmfpwqffpqwmfmwqp"
		},
		{
			color: "silver",
			id: "4532c23kv54v5435vmn52klv2l5mv45l",
			started: "Wed, Sep 2, 2020 8:39 AM",
			bet: "9",
			hash: "nsdfjsdnjkfnssdfgheiushthfshfoaojriojfkrekoppofoewqfqwekeffmwqkfmkwqmfpwqffpqwmfmwqp"
		}, 
		{
			color: "bronze",
			id: "4532c23kv54v5435vmn52klv2l5mv45l",
			started: "Wed, Sep 2, 2020 8:39 AM",
			bet: "9",
			hash: "nsdfjsdnjkfnssdfgheiushthfshfoaojriojfkrekoppofoewqfqwekeffmwqkfmkwqmfpwqffpqwmfmwqp"
		}, 
		{
			color: "silver",
			id: "4532c23kv54v5435vmn52klv2l5mv45l",
			started: "Wed, Sep 2, 2020 8:39 AM",
			bet: "9",
			hash: "nsdfjsdnjkfnssdfgheiushthfshfoaojriojfkrekoppofoewqfqwekeffmwqkfmkwqmfpwqffpqwmfmwqp"
		}, 
		{
			color: "bronze",
			id: "4532c23kv54v5435vmn52klv2l5mv45l",
			started: "Wed, Sep 2, 2020 8:39 AM",
			bet: "9",
			hash: "nsdfjsdnjkfnssdfgheiushthfshfoaojriojfkrekoppofoewqfqwekeffmwqkfmkwqmfpwqffpqwmfmwqp"
		}, 
		{
			color: "silver",
			id: "4532c23kv54v5435vmn52klv2l5mv45l",
			started: "Wed, Sep 2, 2020 8:39 AM",
			bet: "9",
			hash: "nsdfjsdnjkfnssdfgheiushthfshfoaojriojfkrekoppofoewqfqwekeffmwqkfmkwqmfpwqffpqwmfmwqp"
		}, 
		{
			color: "bronze",
			id: "4532c23kv54v5435vmn52klv2l5mv45l",
			started: "Wed, Sep 2, 2020 8:39 AM",
			bet: "9",
			hash: "nsdfjsdnjkfnssdfgheiushthfshfoaojriojfkrekoppofoewqfqwekeffmwqkfmkwqmfpwqffpqwmfmwqp"
		},
		{
			color: "silver",
			id: "4532c23kv54v5435vmn52klv2l5mv45l",
			started: "Wed, Sep 2, 2020 8:39 AM",
			bet: "9",
			hash: "nsdfjsdnjkfnssdfgheiushthfshfoaojriojfkrekoppofoewqfqwekeffmwqkfmkwqmfpwqffpqwmfmwqp"
		}, 
		{
			color: "bronze",
			id: "4532c23kv54v5435vmn52klv2l5mv45l",
			started: "Wed, Sep 2, 2020 8:39 AM",
			bet: "9",
			hash: "nsdfjsdnjkfnssdfgheiushthfshfoaojriojfkrekoppofoewqfqwekeffmwqkfmkwqmfpwqffpqwmfmwqp"
		}, 
		{
			color: "silver",
			id: "4532c23kv54v5435vmn52klv2l5mv45l",
			started: "Wed, Sep 2, 2020 8:39 AM",
			bet: "9",
			hash: "nsdfjsdnjkfnssdfgheiushthfshfoaojriojfkrekoppofoewqfqwekeffmwqkfmkwqmfpwqffpqwmfmwqp"
		},
		{
			color: "bronze",
			id: "4532c23kv54v5435vmn52klv2l5mv45l",
			started: "Wed, Sep 2, 2020 8:39 AM",
			bet: "9",
			hash: "nsdfjsdnjkfnssdfgheiushthfshfoaojriojfkrekoppofoewqfqwekeffmwqkfmkwqmfpwqffpqwmfmwqp"
		}, 
		{
			color: "silver",
			id: "4532c23kv54v5435vmn52klv2l5mv45l",
			started: "Wed, Sep 2, 2020 8:39 AM",
			bet: "9",
			hash: "nsdfjsdnjkfnssdfgheiushthfshfoaojriojfkrekoppofoewqfqwekeffmwqkfmkwqmfpwqffpqwmfmwqp"
		}, 
		{
			color: "bronze",
			id: "4532c23kv54v5435vmn52klv2l5mv45l",
			started: "Wed, Sep 2, 2020 8:39 AM",
			bet: "9",
			hash: "nsdfjsdnjkfnssdfgheiushthfshfoaojriojfkrekoppofoewqfqwekeffmwqkfmkwqmfpwqffpqwmfmwqp"
		}, 
		{
			color: "silver",
			id: "4532c23kv54v5435vmn52klv2l5mv45l",
			started: "Wed, Sep 2, 2020 8:39 AM",
			bet: "9",
			hash: "nsdfjsdnjkfnssdfgheiushthfshfoaojriojfkrekoppofoewqfqwekeffmwqkfmkwqmfpwqffpqwmfmwqp"
		}, 
		{
			color: "bronze",
			id: "4532c23kv54v5435vmn52klv2l5mv45l",
			started: "Wed, Sep 2, 2020 8:39 AM",
			bet: "9",
			hash: "nsdfjsdnjkfnssdfgheiushthfshfoaojriojfkrekoppofoewqfqwekeffmwqkfmkwqmfpwqffpqwmfmwqp"
		},
		{
			color: "silver",
			id: "4532c23kv54v5435vmn52klv2l5mv45l",
			started: "Wed, Sep 2, 2020 8:39 AM",
			bet: "9",
			hash: "nsdfjsdnjkfnssdfgheiushthfshfoaojriojfkrekoppofoewqfqwekeffmwqkfmkwqmfpwqffpqwmfmwqp"
		}, 
		{
			color: "bronze",
			id: "4532c23kv54v5435vmn52klv2l5mv45l",
			started: "Wed, Sep 2, 2020 8:39 AM",
			bet: "9",
			hash: "nsdfjsdnjkfnssdfgheiushthfshfoaojriojfkrekoppofoewqfqwekeffmwqkfmkwqmfpwqffpqwmfmwqp"
		}, 
		{
			color: "silver",
			id: "4532c23kv54v5435vmn52klv2l5mv45l",
			started: "Wed, Sep 2, 2020 8:39 AM",
			bet: "9",
			hash: "nsdfjsdnjkfnssdfgheiushthfshfoaojriojfkrekoppofoewqfqwekeffmwqkfmkwqmfpwqffpqwmfmwqp"
		},
		{
			color: "bronze",
			id: "4532c23kv54v5435vmn52klv2l5mv45l",
			started: "Wed, Sep 2, 2020 8:39 AM",
			bet: "9",
			hash: "nsdfjsdnjkfnssdfgheiushthfshfoaojriojfkrekoppofoewqfqwekeffmwqkfmkwqmfpwqffpqwmfmwqp"
		}, 
		{
			color: "silver",
			id: "4532c23kv54v5435vmn52klv2l5mv45l",
			started: "Wed, Sep 2, 2020 8:39 AM",
			bet: "9",
			hash: "nsdfjsdnjkfnssdfgheiushthfshfoaojriojfkrekoppofoewqfqwekeffmwqkfmkwqmfpwqffpqwmfmwqp"
		}, 
		{
			color: "bronze",
			id: "4532c23kv54v5435vmn52klv2l5mv45l",
			started: "Wed, Sep 2, 2020 8:39 AM",
			bet: "9",
			hash: "nsdfjsdnjkfnssdfgheiushthfshfoaojriojfkrekoppofoewqfqwekeffmwqkfmkwqmfpwqffpqwmfmwqp"
		}, 
		{
			color: "silver",
			id: "4532c23kv54v5435vmn52klv2l5mv45l",
			started: "Wed, Sep 2, 2020 8:39 AM",
			bet: "9",
			hash: "nsdfjsdnjkfnssdfgheiushthfshfoaojriojfkrekoppofoewqfqwekeffmwqkfmkwqmfpwqffpqwmfmwqp"
		}, 
		{
			color: "bronze",
			id: "4532c23kv54v5435vmn52klv2l5mv45l",
			started: "Wed, Sep 2, 2020 8:39 AM",
			bet: "9",
			hash: "nsdfjsdnjkfnssdfgheiushthfshfoaojriojfkrekoppofoewqfqwekeffmwqkfmkwqmfpwqffpqwmfmwqp"
		},
		{
			color: "silver",
			id: "4532c23kv54v5435vmn52klv2l5mv45l",
			started: "Wed, Sep 2, 2020 8:39 AM",
			bet: "9",
			hash: "nsdfjsdnjkfnssdfgheiushthfshfoaojriojfkrekoppofoewqfqwekeffmwqkfmkwqmfpwqffpqwmfmwqp"
		}, 
		{
			color: "bronze",
			id: "4532c23kv54v5435vmn52klv2l5mv45l",
			started: "Wed, Sep 2, 2020 8:39 AM",
			bet: "9",
			hash: "nsdfjsdnjkfnssdfgheiushthfshfoaojriojfkrekoppofoewqfqwekeffmwqkfmkwqmfpwqffpqwmfmwqp"
		}, 
		{
			color: "silver",
			id: "4532c23kv54v5435vmn52klv2l5mv45l",
			started: "Wed, Sep 2, 2020 8:39 AM",
			bet: "9",
			hash: "nsdfjsdnjkfnssdfgheiushthfshfoaojriojfkrekoppofoewqfqwekeffmwqkfmkwqmfpwqffpqwmfmwqp"
		}
	];
</script>

<style>
	@keyframes progress {
	    from {
	        stroke-dashoffset: 0;
	    }
	    to {
	        stroke-dashoffset: 295.31;
	    }
	}
	.info__header{
		padding: 0 16px 56px;
		display: flex;
		height: 144px;
	}
	.info__timer{
		position: relative;
		flex: 0 0 144px;
		min-width: 144px;
		margin-right: 16px;
		background: #222341;
		border-radius: 4px;
		display: flex;
		align-items: center;
		justify-content: center;
		box-shadow: 0px 8px 10px rgba(0, 0, 0, 0.14), 0px 3px 14px rgba(0, 0, 0, 0.12), 0px 4px 5px rgba(0, 0, 0, 0.2);
	}
	.info__timer svg{
		transform: rotate(-90deg);
		position: absolute;
		top:0;
		bottom: 0;
		left: 0;
		right: 0;
		margin: auto;
	}
	.info__timer-value {
	    stroke-dasharray: 295.31;
	    stroke-dashoffset: 295.31;
	    animation: progress 48s infinite 0.6s;
	}
	.info__timer-inner{
		width: 96px;
		text-align: center;
	}
	.info__timer-title{
		letter-spacing: 0.25px;
		font-size: 12px;
		color: #5D60A7;
	}
	.info__timer-starting{
		letter-spacing: 0.25px;
		font-size: 12px;
		color: #8D9BF3;
	}
	.info__timer-clock{
		font-size: 16px;
		letter-spacing: 0.5px;
	}
	.info__profile{
		flex: 1 1;
		overflow: hidden;
		padding: 24px;
		display: flex;
		background: #222341;
		border-radius: 4px;
		box-shadow: 0px 8px 10px rgba(0, 0, 0, 0.14), 0px 3px 14px rgba(0, 0, 0, 0.12), 0px 4px 5px rgba(0, 0, 0, 0.2);
	}
	.info__wrapper{
		flex: 1 1;
		display: flex;
		overflow: hidden;
		flex-direction: column;
		justify-content: space-around;
	}
	.info__name{
		font-weight: 300;
		font-size: 32px;
		text-transform: uppercase;
		white-space: nowrap;
		overflow: hidden;
		text-overflow: ellipsis;
		letter-spacing: 0.25px;
	}
	.info__link{
		letter-spacing: 0.5px;
		font-size: 16px;
		color: #8D9BF3;
		display: inline-block;
		text-decoration: none;
		padding-bottom: 2px;
		border-bottom: 1px solid #8D9BF3;
	}
	.info__balance{
		flex: 0 0 112px;
		border: 1px solid #5D60A7;
		border-radius: 4px;
		padding: 24px 16px;
		box-sizing: border-box;
		text-align: center;
		color: #5D60A7;
		font-size: 12px;
		margin-left: 16px;
	}
	.info__balance-count{
		color: #fff;
		font-weight: bold;
		font-size: 16px;
		margin-top: 8px;
	}
	.info__game{
		position: relative;
		width: 100%;
	}
	.info__game:before{
		content: "";
		position: absolute;
		top: 0;
		left: 50%;
		bottom: 0;
		width: 2px;
		margin-left: -1px;
		background: #8D9BF3;
	}
	.info__list{
		display: flex;
		justify-content: center;/* не знаю как будет реализовано. Временно, чтобы центровалось */
		overflow-x: scroll;
		overflow-y: hidden;
	}
	.info__list::-webkit-scrollbar {
	    display: none;
	}
	.info__item{
		margin: 16px 8px;
		position: relative;
	}
	.info__explorer{
		padding: 24px 16px;
		overflow: hidden;
		display: flex;
		align-items: center;
	}
	.info__explorer-title{
		font-size: 12px;
		margin-right: 16px;
		flex: 0 0 96px;
	}
	.info__history-list{
		flex: 1 1;
		overflow: hidden;
		height: 16px;
	}
	.info__history{
		display: inline-block;
		margin-right: 8px;
	}
	@media (max-width: 1279px) {
		.info__header{
			padding: 0 24px 24px;
		}
		.info__timer{
			flex: 1 1 25%;
		}
		.info__profile{
			flex: 1 1 75%;
		}
		.info__explorer{
			padding: 24px;
		}
	} 
	@media (max-width: 767px) {
		.info__header{
			padding: 16px;
			height: 96px;
		}
		.info__timer{
			background: none;
			box-shadow: none;
			flex: 0 0 96px;
			min-width: 96px;
		}
		.info__profile{
			background: none;
			box-shadow: none;
			flex: 1 1 auto;
			padding: 0;
			flex-direction: column;
			justify-content: center;
		}
		.info__wrapper{
			flex: 0 0 auto;
			flex-direction: row;
			justify-content: space-between;
		}
		.info__balance{
			border:none;
			padding: 0;
			flex: 0 0 auto;
			margin: 0;
			text-align: left;
			font-size: 9px;
		}
		.info__balance-count{
			margin: 0;
			font-size: 14px;
		}
		.info__name{
			font-size: 24px;
			flex: 1 1 auto;
		}
		.info__link{
			font-size: 14px;
		}
		.info__item{
			margin: 8px;
		}
		.info__explorer{
			padding: 8px 16px;
		}
		.info:after{
			content: "Bet amount";
			display: block;
			font-size: 14px;
			border-bottom: 1px solid #5D60A7;
			padding-bottom: 4px;
			margin: 16px 16px 0;
		}
	}
</style>

<div class="info">
	<div class="info__header">
		<div class="info__timer">
			<!-- with timer -->
			<svg width="96" height="96" viewBox="0 0 96 96">
			    <circle cx="48" cy="48" r="47" fill="none" stroke="#8D9BF3" stroke-width="2"
			        stroke-dasharray="295.31" stroke-dashoffset="295.31" class="info__timer-value" />
			</svg>
			<div class="info__timer-inner">
				<div class="info__timer-title">Rolling in:</div>
				<div class="info__timer-clock">05:00</div>
			</div>
			<!-- end with timer -->
			<!-- starting -->
			<!-- <div class="info__timer-inner">
				<div class="info__timer-starting">Game Starting...</div>
			</div> -->
			<!-- end starting -->
		</div>
		<div class="info__profile">
			<div class="info__wrapper">
				<div class="info__name">Davidson</div>
				<div class="info__help">
					<a href="#" class="info__link">Help</a>
				</div>
			</div>
			<div class="info__balance">
				Balance:
				<div class="info__balance-count">27.34$</div>
			</div>
		</div>
	</div>
	<div class="info__game">
		<div class="info__list">
			{#each game as { color }}
				<div class="info__item">
					<Coin color="{color}" />
				</div>
			{/each}
		</div>
	</div>
	<div class="info__explorer">
		<div class="info__explorer-title">Game Explorer</div>
		<div class="info__history-list">
			{#each explorer as { color }, i}
				<div class="info__history">
					<a data-index={i} on:click="{historyClick}" href="#" class="info__history-link">
						<Coin size="small" color="{color}" />
					</a>
				</div>
			{/each}
			{#if showModal}
				<Modal on:close="{() => showModal = false}">
					<span slot="id">{explorer[indexModal].id}</span>
					<span slot="started">{explorer[indexModal].started}</span>
					<span slot="bet">{explorer[indexModal].bet}</span>
					<span slot="hash">{explorer[indexModal].hash}</span>
					<span slot="color">{explorer[indexModal].color}</span>
				</Modal>
			{/if}
		</div>
	</div>
</div>