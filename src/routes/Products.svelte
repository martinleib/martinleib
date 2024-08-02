<script>
    import v1kit from "../img/martinleib_v1_kit.jpg";
    import shivers from "../img/shivers_portal_bank.png";
    import enigma from "../img/enigma_one_shot_kit.jpg";
    import experimental from "../img/experimental_bundle.jpg";

    const kits = [
        {name: "V1 Kit", price: 49.99, img: v1kit, author: "MARTINLEIB", route: "/products/v1-kit"},
        {name: "Shivers Portal Bank", price: 24.99, img: shivers, author: "MARTINLEIB", route: "/products/shivers-portal-bank"},
        {name: "Enigma One-shot Kit", price: 24.99, img: enigma, author: "MARTINLEIB", route: "/products/enigma-one-shot-kit"},
        {name: "Experimental Bundle", price: 59.99, img: experimental, author: "MARTINLEIB", route: "/products/experimental-bundle"}
        ];
</script>

<main class="pt-5 pb-5 akkurat container text-uppercase text-center">
    <div class="row">
        {#each kits as kit (kit.name)}
        <div class="col-12 col-md-3 pb-3 pb-md-0 product-box">
            <a href={kit.route} class="kit-referral">
                <img src={kit.img} alt={kit.name} class="img-fluid product-img" />
                <div class="product-box__info text-center">
                    <p class="m-0 p-0">{kit.name}</p>
                    <p class="m-0 p-0 fs-7">{kit.author}</p>
                    <p class="m-0 p-0 product-box__price">${kit.price}</p>
                </div>
            </a>
        </div>
        {/each}
    </div>
</main>
