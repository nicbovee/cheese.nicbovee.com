<script context="module" lang="ts">
	export const prerender = true;
	import { theCheese } from '$lib/theCheese';


</script>
<script>
	import Layout from "./__layout.svelte";

	let clickCount = 0;
	let isFlipped = false;

	function toggleFlip(){
		if(clickCount <= 3){
			clickCount++
		} else {
			clickCount = 0;
			isFlipped = !isFlipped;
		}
	}

	let words = "";

</script>
<svelte:head>
	<title>The Incomplete Wisconsin Cheese List</title>
	<meta name="description" content="A place to help me keep track of the cheeses I've tried." />
</svelte:head>

<section class="bg-white" />

<section class="flex flex-col md:flex-row">
	<div class="md:w-2/3 mr-0 md:mr-12">
		<h2 class="text-xl leading-6 font-medium text-gray-900 my-4">The Cheese <span class:mega={isFlipped} class="cheese">🧀<span></h2>

		<ul role="list" class="divide-y divide-gray-200 border-b border-gray-200">
			{#each theCheese as curd}
				<li class="relative bg-white py-5 px-4 ">
					<div class="flex justify-between space-x-3">
						<div class="min-w-0 flex-1">
							<span class="absolute inset-0" aria-hidden="true" />
							<p class="text-sm font-medium text-gray-900 truncate">
								<span class="flex-shrink-0 whitespace-nowrap text-sm text-gray-500"
									>{curd.manufacturer}</span
								>
								– {curd.name}
							</p>
						</div>
					</div>
					<div class="mt-1">
						<p class="line-clamp-2 text-sm text-gray-600">
							 "{curd.notes}"
						</p>
					</div>
					<p class="text-xs text-gray-500 truncate mt-6">{curd.type}</p>
				</li>
			{/each}
		</ul>
	</div>
	<aside  on:click={toggleFlip} class=" md:w-1/3 bg-slate-100 p-6">
	<div  class:flip={isFlipped} class="transition-ease">
		<h1 class="text-3xl leading-normal font-medium text-gray-900 pb-4">
			The <br />Incomplete <br />Wisconsin <br />Cheese List.
		</h1>
		<h2 class="text-red text-xl leading-6 font-medium text-gray-900 my-4">Why does this exist?</h2>
		<p>
			Since 2018, my friends and I have traveled from Colorado to Wisconsin to find the freshest
			cheese curds. What began as a simple search for the squeak has become a biennial tradition to
			find the best cheeses in Wisconsin. On our most recent trip in 2022 I realized that I
			completely forgot what cheeses I liked and didn't like from our previous visits. Part of that
			list is here.
		</p>
	</div>
	</aside>
</section>
<style>
	.transition-ease {
		transition: all ease-in-out 1000ms;
	}
	.flip {
		display: block;
		transform: rotate(180deg)
	}
	.cheese {		
		position: absolute;

z-index: 10000;
	transition: all ease-in-out 4000ms;
font-size: 2rem;
	}
	.mega {

		transform: scale(20) translateX(2vw) translateY(2vh);
		
	}
</style>