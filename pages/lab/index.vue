<script setup>
const { data: posts } = await useAsyncData('posts', () =>
	queryContent('/blog').find()
);

useHead({
	title: 'OOYOO - THE LAB',
	meta: [
		{
			name: 'description',
			content: 'The Design + Development Lab @ OOYOO',
		},
	],
	script: [{ innerHTML: "console.log('Hello world')" }],
});
</script>

<template>
	<h1 class="text-3xl my-8">THE LAB: Design + Development</h1>

	<h2 class="">Internal Agency</h2>
	<p>
		The fulcrum and driving force behind innovation at OOYOO, THE LAB stands as
		an incubator of creativity and ingenuity, fueling the brand's own identity
		and products. As OOYOO's exclusive Internal Design + Development Studio, it
		meticulously crafts our brands, breathing life into its unique story through
		captivating branding and meticulously designed products.
	</p>

	<h2 class="">Creative Service Consultations</h2>
	<p>
		THE LAB is a nexus of collaboration where design meets culture and
		technology in perfect harmony. With a remarkable track record of breathing
		life into ideas, it transforms visions into tangible realities, while also
		guiding external clients on their own creative journeys. Capitalizing on our
		expertise and network.
	</p>
	<p>
		Beyond its role within OOYOO, THE LAB extends its expert hand to the wider
		creative landscape, offering its profound insights and artistic prowess to
		external brands and small businesses through tailored consultations.
	</p>
	<p>
		Whether you're an established brand seeking rejuvenation or a small business
		with big dreams, THE LAB's multidisciplinary team of visionaries is poised
		to elevate your identity, invigorate your presence, and empower your
		aspirations.
	</p>

	<section class="grid md:grid-cols-3 mt-8 gap-5">
		<Post :posts="posts" />
	</section>
</template>
