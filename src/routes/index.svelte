<script context="module" lang="ts">
	export const prerender = true;

	const theCheese = [
		{
			name: 'Butterkase',
			manufacturer: 'Carr Valley',
			type: `Cow's milk`,
			notes: `It really tastes like butter. Probably in my top 10 for Carr Valley.`
		},
		{
			name: 'Garlic Bread Cheese',
			manufacturer: 'Carr Valley',
			type: 'Bread Cheese',
			notes: `Always a winner and probably better than the pizza bread cheese.`
		},
		{
			name: 'Widmers 6 Year',
			manufacturer: 'Widmers',
			type: 'Cheddar',
			notes: `Good price per pound for aged cheddar. Good flavor and not to sharp.`
		},
		{
			name: '12 Year Cheddar',
			manufacturer: 'Carr Valley',
			type: 'Cheddar',
			notes: `Probably not worth the price. It's kind of past the point of sharpness that is pleasant. Glad to have tried it, and would get a smaller brick of it in the future.`
		},
		{
			name: '5 Year Cheddar',
			manufacturer: 'Hooks',
			type: 'Cheddar',
			notes:
				'I would definitely like to try hooks other cheeses after trying this one. It tasted about as sharp as Carr valley, but somehow I felt like the flavor was better.'
		},
		{
			name: 'Porto Duet',
			manufacturer: 'Carr Valley',
			type: 'Sheep Milk',
			notes: 'More wine flavor than expected but I think everyone who tried it seemed to enjoy it.'
		},
		{
			name: '3 Year Reserve Cheddar',
			manufacturer: 'Deer Creek',
			type: 'Cheddar',
			notes: 'This was a white cheddar that was the perfect amount of sharpness.'
		}
	];
</script>

<svelte:head>
	<title>The Incomplete Wisconsin Cheese List</title>
	<meta name="description" content="A place to help me keep track of the cheeses I've tried." />
</svelte:head>

<section class="bg-white" />

<section class="flex flex-col md:flex-row">
	<div class="md:w-2/3 mr-0 md:mr-12">
		<h2 class="text-xl leading-6 font-medium text-gray-900 my-4">The Cheese 🧀</h2>

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
	<aside class="md:w-1/3 bg-slate-100 p-6">
		<h1 class="text-3xl leading-normal font-medium text-gray-900 pb-4">
			The <br />Incomplete <br />Wisconsin <br />Cheese List.
		</h1>
		<h2 class="text-xl leading-6 font-medium text-gray-900 my-4">Why does this exist?</h2>
		<p>
			Since 2018, my friends and I have traveled from Colorado to Wisconsin to find the freshest
			cheese curds. What began as a simple search for the squeak has become a biennial tradition to
			find the best cheeses in Wisconsin. On our most recent trip in 2022 I realized that I
			completely forgot what cheeses I liked and didn't like from our previous visits. Part of that
			list is here.
		</p>
	</aside>
</section>
