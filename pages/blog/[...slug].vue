<script setup>
// The useRoute() hook is a Nuxt.js hook that is used to access the current route. The useRoute() hook returns an object with information about the current route, including the path, the params, and the query.

// https://nuxt.com/docs/api/composables/  — Composables are Nuxt Hooks out the box.

const { path } = useRoute();

// The useAsyncData() hook is a Nuxt.js hook that is used to fetch data from an asynchronous source before the component is rendered. The useAsyncData() hook returns an object with the data that was fetched.

// The first argument is the name of the asynchronous source. This can be a URL, a function, or an object.

//The second argument is an optional function that is called after the data has been fetched. This function can be used to modify the data before it is returned.

// The useRoute() hook will first return information about the current route. The path property will contain the path of the current route. The params property will contain the params of the current route. The query property will contain the query of the current route.

//In this example, the asyncData function does not modify the route information. The asyncData function simply returns the route information that was returned by the useRoute() hook.

// In the code you provided, the `where()` method is used to filter the results to only include content objects where the `_path` property is equal to the value of the `path` variable. This means that the `queryContent()` function will only return the content object at the path `/blog/my-post`.

// If the content object at the path `/blog/my-post` does not exist, then the value of the `content-{path}variable will be undefined`.

// { data } bring back all the content from the .md and we then have access to any Front Matter

const { data } = await useAsyncData(`content-${path}`, () => {
	return queryContent().where({ _path: path }).findOne();
});
</script>

<template>
	<!-- <p>{{ $route.params.slug }}</p> -->
	<!-- <ContentDoc class="prose" /> -->
	<!-- <ContentDoc> works fine and simply if you all you want to do is display the content from the .MD; it automatically gets the data. But as soon as you introduce more data and need access to it, like the Front Matter, you have to write a script to get it the data using queryContent() as well as use <ContentRenderer> https://content.nuxtjs.org/guide/displaying/rendering -->
	<Head><Title>Nuxt Dojo</Title></Head>
	<ContentRenderer :value="data" class="prose my-10 mx-auto max-w-7xl" />
	<div class="my-8">
		<a
			v-for="tag in data.tags"
			:key="tag"
			:href="`/blog/tags/${tag}`"
			class="text-sm font-semibold inline-block py-2 px-4 rounded-lg text-gray-100 bg-blue-500 uppercase last:mr-0 mr-4"
		>
			<Icon name="ion:pricetags-sharp" size="1rem" class="text-gray-100 mr-2" />
			{{ tag }}
		</a>
	</div>
</template>
