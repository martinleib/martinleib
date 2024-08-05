<script>
    import { User } from './classes.js'
    import Icon from "@iconify/svelte"

    // Datos de ejemplo

    import v1kit from "../../img/martinleib_v1_kit.jpg";
    import shivers from "../../img/shivers_portal_bank.png";
    import enigma from "../../img/enigma_one_shot_kit.jpg";
    import experimental from "../../img/experimental_bundle.jpg";
    import hihatizer from "../../img/hihatizer.jpeg"

    let currentUser = new User(
        "Martin Leib",
        [{
            kitname: "V1 Kit",
            image: v1kit,
            download: "https://drive.google.com",
        },
        {
            kitname: "Shivers Portal Bank",
            image: shivers,
            download: "https://drive.google.com",
        },
        {
            kitname: "Enigma One Shot Kit",
            image: enigma,
            download: "https://drive.google.com",
        },
        {
            kitname: "Experimental Bundle",
            image: experimental,
            download: "https://drive.google.com",
        },
        {
            kitname: "Hihatizer",
            image: hihatizer,
            download: "https://drive.google.com",
        }]
    )
</script>

<svelte:head>
    <title>Your downloads | Martin Leib</title>
    <meta name="description" content="Your downloads" />
</svelte:head>

<div class="container mt-5">
    <h1 class="fs-3">Welcome, {currentUser.name}</h1>
    <h2 class="fs-5">Your downloads:</h2>

    <div class="row text-uppercase akkurat mt-5">
        {#each currentUser.kits as kit (kit)}
            <div class="col-12 col-md-3 pb-3 pb-md-0 product-box mb-0 mb-sm-3 mb-lg-5 pb-3">
                    <img
                        src={kit.image}
                        alt={kit.kitname}
                        class="img-fluid product-img"
                    />
                    <div class="product-box__info text-center">
                        <p class="m-0 p-0">{kit.kitname}</p>
                        <p class="m-0 p-0 fs-7">MARTIN LEIB</p>
                        <a href={kit.download} class="kit-referral btn btn-outline-secondary text-dark mt-2"><Icon icon="bxs:download" /> Download</a>
                    </div>
                </div>
        {/each}
    </div>
</div>