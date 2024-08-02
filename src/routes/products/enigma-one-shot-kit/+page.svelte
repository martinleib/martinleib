<script>
	import Icon from '@iconify/svelte';
	import enigma from "../../../img/enigma_one_shot_kit.jpg";
	const kit = [{name: "Enigma One-Shot Kit", price: 24.99, img: enigma, author: "MARTINLEIB", route: "/products/enigma-one-shot-kit"}]
</script>

<svelte:head>
	<title>{kit[0].name} | Martin Leib</title>
	<meta name="description" content="About this app" />
</svelte:head>

<div class="row pt-5 pb-5">
	<section class="product-box col-12 col-md-6 text-center ps-0 ps-md-5">
		<figure class="figure">
			<img src={kit[0].img} alt={kit[0].name} class="figure-img img-fluid product-img" />
		</figure>
	</section>

	<section class="product-box col-12 col-md-6 pe-0 pe-md-5 pt-5 pt-md-0 text-center">
		<div class="product-box__info text-center">
			<h1 class="m-0 p-0">{kit[0].name}</h1>
			<p class="m-0 p-0 product-box__price fs-3">${kit[0].price}</p>
			<p class="mt-5p-0 product-box__info fs-5">it includes:</p>
			<ul class="list-unstyled">
				<li>90 one-shot samples best suited for <em>Ambient</em> and <em>Virtual</em> beats</li>
			</ul>
		</div>

		<section class="product-box__buttons">
			<button class="btn btn-primary"><Icon icon="mdi:cart" /> Add to cart</button>
			<button class="btn btn-warning"><Icon icon="cib:paypal" /> Checkout with PayPal</button>
		</section>
	</section>
</div>