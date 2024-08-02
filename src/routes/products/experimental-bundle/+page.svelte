<script>
	import Icon from '@iconify/svelte';
	import experimental from "../../../img/experimental_bundle.jpg";
	const kit = [{name: "Experimental Bundle", price: 59.99, img: experimental, author: "MARTINLEIB", route: "/products/experimental-bundle"}]
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
				<li>Includes <em>the Experimental Soundkit Vol. 1</em>, <em>the Experimental Soundkit Vol. 2</em>, <em>the Pandora Kit</em> and <em>the Spire Bank vol. 1</em> totalling:</li>
				<br>
				<li>259 drum sounds</li>
				<li>55 foley recordings</li>
				<li>10 one-shots</li>
				<li>48 midis</li>
				<li>7 loops</li>
				<li>7 FLPs</li>
				<li>94 FL Studio presets</li>
			</ul>
		</div>

		<section class="product-box__buttons">
			<button class="btn btn-primary"><Icon icon="mdi:cart" /> Add to cart</button>
			<button class="btn btn-warning"><Icon icon="cib:paypal" /> Checkout with PayPal</button>
		</section>
	</section>
</div>