<script context="module">
	export function preload({ params, query }) {
		return this.fetch(`blog.json`).then(r => r.json()).then(posts => {
			return { posts };
		});
	}
</script>

<script>
	export let posts;
</script>

<style>

	figure {
		margin: 0 0 0 0;
	}

	/* img {
		width: 100%;
		margin: 0 0 1em 0;
	}

	.image:hover > .overlay {
		width:100%;
		height:100%;
		background-color:#000;
		opacity:0.5;
	} */
	img {
		width: 100%;
		-webkit-transition: all 0.5s ease;
		-moz-transition: all 0.3s ease;
		-o-transition: all 0.3s ease;
		-ms-transition: all 0.3s ease;
		transition: all 0.3s ease;
	}

	img:hover {
		-webkit-filter: brightness(70%);
		filter: brightness(70%);
	}

</style>

<svelte:head>
	<title>Daniella Kaligorsky Portfolio</title>
</svelte:head>

<h1><b>Daniella Kaligorsky</b></h1>

<figure>
	{#each posts as post}
		<!-- we're using the non-standard `rel=prefetch` attribute to
				tell Sapper to load the data for the page as soon as
				the user hovers over the link or taps it, instead of
				waiting for the 'click' event -->
		<a class="image" rel='prefetch' href='blog/{post.slug}'>
			<img class="overlay" rel='prefetch' src="{post.thumbnail}" alt="">
		</a>
		
		<p>{post.title}</p>
	{/each}
</figure>

