<script>
    import v1kit from "../img/martinleib_v1_kit.jpg";
    import shivers from "../img/shivers_portal_bank.png";
    import enigma from "../img/enigma_one_shot_kit.jpg";
    import experimental from "../img/experimental_bundle.jpg";
    import hihatizer from "../img/hihatizer.jpeg"

    import { onMount } from 'svelte';

    let kits = [];
    let selectedCategory = "all";

    const allProducts = [
        {
            name: "V1 Kit",
            price: 49.99,
            img: v1kit,
            category: "drumkit",
            author: "MARTINLEIB",
            route: "/products/v1-kit",
        },
        {
            name: "Shivers Portal Bank",
            price: 24.99,
            img: shivers,
            category: "portal",
            author: "MARTINLEIB",
            route: "/products/shivers-portal-bank",
        },
        {
            name: "Enigma One-shot Kit",
            price: 24.99,
            img: enigma,
            category: "oneshot",
            author: "MARTINLEIB",
            route: "/products/enigma-one-shot-kit",
        },
        {
            name: "Experimental Bundle",
            price: 59.99,
            img: experimental,
            category: "drumkit",
            author: "MARTINLEIB",
            route: "/products/experimental-bundle",
        },
        {
            name: "Hihatizer",
            price: 24.99,
            img: hihatizer,
            category: "plugin",
            author: "MARTINLEIB",
            route: "/products/hihatizer"
        }
    ];

    const handleProductsByCategory = (category) => {
        if (selectedCategory === category) {
            selectedCategory = "all";
            kits = allProducts;
            removeActiveClass(category);
        } else {
            selectedCategory = category;
            kits = category === "all" ? allProducts : allProducts.filter((kit) => kit.category === category);
            handleActiveClass(category);
        } 
    };

    const handleActiveClass = (category) => {
        const drumkitButton = document.querySelector("#btn-category__drumkit");
        const portalButton = document.querySelector("#btn-category__portal");
        const oneshotButton = document.querySelector("#btn-category__oneshot");
        const pluginButton = document.querySelector("#btn-category__plugin");

        switch (category) {
            case "drumkit":
                drumkitButton.classList.add("active");
                portalButton.classList.remove("active");
                oneshotButton.classList.remove("active");
                pluginButton.classList.remove("active");
                break;
            case "portal":
                portalButton.classList.add("active");
                drumkitButton.classList.remove("active");
                oneshotButton.classList.remove("active");
                pluginButton.classList.remove("active");
                break;
            case "oneshot":
                oneshotButton.classList.add("active");
                drumkitButton.classList.remove("active");
                portalButton.classList.remove("active");
                pluginButton.classList.remove("active");
                break;
            case "plugin":
                pluginButton.classList.add("active");
                drumkitButton.classList.remove("active");
                portalButton.classList.remove("active");
                oneshotButton.classList.remove("active");
        }   
    }

    const removeActiveClass = (category) => {
        const drumkitButton = document.querySelector("#btn-category__drumkit");
        const portalButton = document.querySelector("#btn-category__portal");
        const oneshotButton = document.querySelector("#btn-category__oneshot");
        const pluginButton = document.querySelector("#btn-category__oneshot");

        switch (category) {
            case "drumkit":
                drumkitButton.classList.remove("active");
                break;
            case "portal":
                portalButton.classList.remove("active");
                break;
            case "oneshot":
                oneshotButton.classList.remove("active");
                break;
            case "plugin":
                pluginButton.classList.remove("active");
                break;
        }        
    }

    onMount(() => {
        handleProductsByCategory("all");
    });
</script>

<main class="pt-5 pb-5 container text-center">
    <div class="text-start mb-3">
        <button class="btn btn-dark mb-1 mb-sm-0" id="btn-category__drumkit" on:click={() => handleProductsByCategory("drumkit")}>Drum Kits</button>
        <button class="btn btn-dark mb-1 mb-sm-0" id="btn-category__portal" on:click={() => handleProductsByCategory("portal")}>Portal Banks</button>
        <button class="btn btn-dark mb-1 mb-sm-0" id="btn-category__oneshot" on:click={() => handleProductsByCategory("oneshot")}>One-shot Kits</button>
        <button class="btn btn-dark mb-1 mb-sm-0" id="btn-category__plugin" on:click={() => handleProductsByCategory("plugin")}>Plugins</button>
    </div>
    <hr>
    <div class="row text-uppercase akkurat">
        {#each kits as kit (kit.name)}
            <div class="col-12 col-md-3 mb-0 mb-sm-3 mb-lg-5 pb-3 pb-md-0 product-box">
                <a href={kit.route} class="kit-referral">
                    <img
                        src={kit.img}
                        alt={kit.name}
                        class="img-fluid product-img"
                    />
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
