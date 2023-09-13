<script setup>
const { data: posts } = await useAsyncData('posts', () =>
	queryContent('/blog').find()
);

useHead({
	title: 'OOYOO - O&O Properties',
	meta: [
		{
			name: 'description',
			content:
				"OOYOO's portfolio of properties and assets which also include brands, products and services.",
		},
	],
	script: [{ innerHTML: "console.log('Hello world')" }],
});
</script>

<template>
	<section class="bg-gray-200 p-8">
		<h1 class="text-4xl">Owned & <br />Operated</h1>

		<p>
			Our portfolio of properties and assets which include brands, products and
			services.
		</p>
	</section>
	<section class="mt-4 bg-gray-300 p-8">
		<p>
			As a parent company, OOYOO, nurtures a diverse ecosystem of digital and
			physical products, services, and brands that have sprung to life under its
			vision and guidance. All of the properties in our dynamic and
			ever-evolving portfolio which sit at the intersection point of culture,
			media, and cutting-edge technology across various industries are all owned
			and operated for us and by us.
		</p>
		<div>
			<div class="h-500 bg-grey-400">Brand 1</div>
			<div class="h-500 bg-grey-400">Brand 2</div>
			<div class="h-500 bg-grey-400">Brand 3</div>
			<div class="h-500 bg-grey-400">Brand 4</div>
		</div>
	</section>

	<section class="mt-4 bg-gray-300 p-8">
		<h3 class="text-3xl">Partners & Collaboration</h3>
		<p>
			Lorem ipsum dolor sit amet consectetur adipisicing elit. Quo minima vitae
			voluptates, placeat expedita ipsam magnam cumque amet sapiente corrupti
			dolores minus deserunt quia architecto!
		</p>
	</section>
	<section class="mt-4 bg-gray-300 p-8">
		<h4 class="text-2xl">Diversity</h4>
		<p>Minority & Women owned.</p>

		<p>
			They're all minority and women owned. We believe in the strength of
			diversity.
		</p>
	</section>
	<section class="mt-4 bg-gray-300 p-8">
		<h4 class="text-2xl">Brand Pillars</h4>
		<p>We believe in:</p>
		<ul>
			<li>Community: the importance of human connection.</li>
			<li>
				Sharing: Distribution of wealth and all of those who help build and use
				the app will share in the growth.
			</li>
			<li>Taxes: Paying our fair share.</li>
			<li>Environment: Leaving the planet a little better than before.</li>
		</ul>

		<h4>Charity: Giving back. An</h4>
	</section>
</template>
