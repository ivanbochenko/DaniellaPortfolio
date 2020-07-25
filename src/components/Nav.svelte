<script>
	export let segment;
</script>

<style>
	nav {
		border-bottom: 1px solid rgba(0,0,0,0.1);
		padding: 1em 2em 1em;
		box-shadow: 0px 3px 3px -2px rgba(0,0,0,.2);
	 	position: fixed;
		top: 0;
		left: 0;
		z-index: 9999;
		width: 100%;
		height: 40px;
		background-color: white;
	}


	.a {
		text-decoration: none;
		padding: 0.5em 1em;
		display: block;
	}
	

	ul {
		margin: 0;
		padding: 0;
	}


	li {
		display: block;
		float: left;
	}
	.logo{
		left: 46.8%;
		position: absolute;
		top: -2px;		
	}
	.icons{		
		display: block;
		float: right;
		padding: 0.5em 5em 0em ;
	}

	.icon{
		padding: 0em 0.5em  ;
			
		display: block;
		float: left;
	}

	[aria-current] {
		font-weight: 600;
	}

</style>

<nav>
	<div>
		<ul>
			<li><a class="a" aria-current='{segment === "about" ? "page" : undefined}' href='about'>About</a></li>
			<li><a class="a" aria-current='{segment === undefined ? "page" : undefined}' href='.'>Work</a></li>
			<li><a class="a" aria-current='{segment === "contact" ? "page" : undefined}' href='contact'>Contact</a></li>

			<!-- for the blog link, we're using rel=prefetch so that Sapper prefetches
				the blog data when we hover over the link or tap it on a touchscreen -->
			<li><a class="a" rel=prefetch aria-current='{segment === "blog" ? "page" : undefined}' href='blog'>Blog</a></li>
			
		</ul>
	</div>
	<div>
		<h1 class="logo">DK</h1>
	</div>
	<div class="icons">
		<a class="icon" href="#"><img src="behance.svg" alt=""></a>
		<a class="icon" href="#"><img src="linkedin.svg" alt=""></a>
		<a class="icon" href="#"><img src="instagram.svg" alt=""></a>
	</div>
	
</nav>
