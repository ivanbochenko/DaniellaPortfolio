<script>
    export let picture
    export let title
    export let description
</script>

<style>


	div {
		margin: 0 0 0 0;
		padding: 0 0 0 0;
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
		z-index: -1;
		width: 100%;
		-webkit-transition: all 0.5s ease;
		-moz-transition: all 0.3s ease;
		-o-transition: all 0.3s ease;
		-ms-transition: all 0.3s ease;
		transition: all 0.3s ease;
	}

	img:hover {
		-webkit-filter: brightness(60%);
		filter: brightness(60%);
	}
	.img__description {
		position: relative;
		top: 0%;
		left: 0%;
		/* color: #fff; */
		visibility: hidden;
		opacity: 0;

	}

	.img__wrap:hover .img__description {
		visibility: visible;
		opacity: 1;
	}

</style>

<div class="img__wrap">
    <a href="#">
        <img src="{picture}" alt="">
    </a>
    <div class="img__description">
    
        <p >{title}</p>
        {@html description}
    </div>
</div>