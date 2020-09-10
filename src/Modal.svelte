<script>
	import { createEventDispatcher, onDestroy } from 'svelte';

	const dispatch = createEventDispatcher();
	const close = () => dispatch('close');

	let modal;

	const handle_keydown = e => {
		if (e.key === 'Escape') {
			close();
			return;
		}

		if (e.key === 'Tab') {
			// trap focus
			const nodes = modal.querySelectorAll('*');
			const tabbable = Array.from(nodes).filter(n => n.tabIndex >= 0);

			let index = tabbable.indexOf(document.activeElement);
			if (index === -1 && e.shiftKey) index = 0;

			index += tabbable.length + (e.shiftKey ? -1 : 1);
			index %= tabbable.length;

			tabbable[index].focus();
			e.preventDefault();
		}
	};

	const previously_focused = typeof document !== 'undefined' && document.activeElement;

	if (previously_focused) {
		onDestroy(() => {
			previously_focused.focus();
		});
	}
</script>

<style>
	.modal-background {
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		background: rgba(0,0,0,0.8);
	}
	.modal {
		position: absolute;
		left: 50%; 
		top: 50%;
		width: 650px;
		max-width: 100%;
		max-height: 100%;
		overflow: auto;
		transform: translate(-50%,-50%);
		padding: 32px 48px;
		box-sizing: border-box;
		border-radius: 4px;
		background: #222341;
		box-shadow: 0px 8px 10px rgba(0, 0, 0, 0.14), 0px 3px 14px rgba(0, 0, 0, 0.12), 0px 4px 5px rgba(0, 0, 0, 0.2);
	}
	.modal__header{
		position: relative;
		padding: 0 30px 4px 0;
		border-bottom: 1px solid #5D60A7;
		font-size: 24px;
		font-weight: 300;
	}
	.modal__close{
		display: block;
		position: absolute;
		right: 5px;
		top:12px;
		width: 14px;
		height: 14px;
		background: none;
		border: none;
		padding: 0;
		margin: 0;
		cursor: pointer;
	}
	.modal__close:before,
	.modal__close:after{
		content: "";
		position: absolute;
		top: 50%;
		left: -3px;
		right: -3px;
		height: 2px;
		background: #5D60A7;
	}
	.modal__close:before{
		transform: translateY(-50%) rotate(45deg);
	}
	.modal__close:after{
		transform: translateY(-50%) rotate(-45deg);
	}
	.modal__id{
		padding: 16px 0;
		letter-spacing: 0.5px;
	}
	.modal__line{
		letter-spacing: 0.5px;
	}
	.modal__title{
		display: inline-block;
		font-weight: bold;
		color: #5D60A7;
	}
	.modal__text{
		display: inline-block;
		word-wrap: break-word;
		max-width: 100%;
	}
	@media (max-width: 767px) {
		.modal{
			width: 100%;
			height: 100%;
			padding: 16px;
		}
		.modal__header{
			padding: 40px 0 4px;
			font-size: 20px;
		}
		.modal__body{
			font-size: 14px;
		}
	}
</style>

<svelte:window on:keydown={handle_keydown}/>

<div class="modal-background" on:click={close}></div>

<div class="modal" role="dialog" aria-modal="true" bind:this={modal}>
	<div class="modal__header">
		<button on:click={close} class="modal__close"></button>
		Game Explorer - Roulette Game
	</div>
	<div class="modal__body">
		<div class="modal__id">Id: <slot name="id"></slot></div>
		<div class="modal__line">
			<div class="modal__title">Sterted At:</div>
			<div class="modal__text"><slot name="started"></slot></div>
		</div>
		<div class="modal__line">
			<div class="modal__title"># of Bets:</div>
			<div class="modal__text"><slot name="bet"></slot></div>
		</div>
		<div class="modal__line">
			<div class="modal__title">Hash:</div>
			<div class="modal__text"><slot name="hash"></slot></div>
		</div>
		<div class="modal__line">
			<div class="modal__title">Winning Color:</div>
			<div class="modal__text"><slot name="color"></slot></div>
		</div>
	</div>
</div>
