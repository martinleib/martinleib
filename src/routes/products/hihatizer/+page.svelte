<script>
	import Icon from '@iconify/svelte';
	import hihatizer from "../../../img/hihatizer.jpeg";
	const kit = [{name: "Hihatizer", price: 24.99, img: hihatizer, author: "MARTINLEIB", route: "/products/hihatizer"}]
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
				<li>transform your percussions using this plugin powered by Patcher for FL Studio 20 and 21. all the paid third-party plugins used can be seemlessly switched to stock plugins: even if you don't own them, you can just replace them or turn them off.</li>
                <br>
                <li>the free VST codec is used in this patch. you can get it for free here: https://lese.io/plugin/codec/</li>
                <br>
                <li>other third-party plugins used include Timeless 3 by Fabfilter. while it isn't necessary, it's recommended. if you don't own it you can click on the button that says Stock/Fabfilter to switch it for Fruity Delay 3. same applies for Effectrix, while it's recommended, it isn't essential. you can just click the button that says On/Off if you don't have it to turn it off.</li>                    
                <br>
                <li>works both on Mac and Windows, both FL Studio 20 and 21</li>
			</ul>
		</div>

		<section class="product-box__buttons">
			<button class="btn btn-primary"><Icon icon="mdi:cart" /> Add to cart</button>
			<button class="btn btn-warning"><Icon icon="cib:paypal" /> Checkout with PayPal</button>
		</section>
	</section>
</div>