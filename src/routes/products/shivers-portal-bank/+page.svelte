<script>
	import Icon from '@iconify/svelte';
	import shivers from "../../../img/shivers_portal_bank.png";
	const kit = [{name: "Shivers Portal Bank", price: 24.99, img: shivers, author: "MARTINLEIB", route: "/products/shivers-portal-bank"}]
</script>

<svelte:head>
	<title>{kit[0].name} | Martin Leib</title>
	<meta name="description" content="{kit[0].name} by Martin Leib" />
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
			<p class="p-0 product-box__info fs-5">it includes:</p>
			<ul class="list-unstyled">
				<li>25 original presets for <a href="https://output.com/products/portal" target="_blank">Portal</a> created by producer Martin Leib</li>
			</ul>
		</div>

		<section class="product-box__buttons">
			<button class="btn btn-primary"><Icon icon="mdi:cart" /> Add to cart</button>
			<button class="btn btn-warning"><Icon icon="cib:paypal" /> Checkout with PayPal</button>
		</section>
	</section>
</div>