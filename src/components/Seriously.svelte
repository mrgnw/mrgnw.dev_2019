<script>
import { elasticOut } from 'svelte/easing';

function whoosh(node, params) {
		const existingTransform = getComputedStyle(node).transform.replace('none', '');

		return {
			delay: params.delay || 0,
			duration: params.duration || 400,
			easing: params.easing || elasticOut,
			css: (t, u) => `transform: ${existingTransform} scale(${t})`
		};
	}
	
</script>

<div in:whoosh><slot></slot></div>

<style>
	div {
		background: pink;
		border: 23px solid orange;
		padding: 0 15px;
		width: 400px;
		text-align: center;
		transform: translateX(-50px);
		animation: 2s slide infinite alternate ease-in-out;
	}

	@keyframes slide {
		from {
			transform: translateX(-50px)
		}
		to {
			transform: translateX(50px)
		}

	}
</style>
