<script>
    import { fade } from 'svelte/transition';
    import Icon from "@iconify/svelte";

    let showNavbar = false;
    let showCart = false;

    function toggleNavbar() {
        showNavbar = !showNavbar;
        if (showNavbar) {
            document.body.style.overflow = 'hidden';
        } else {
            document.body.style.overflow = 'auto';
        }
    }

    function toggleCart() {
        showCart = !showCart;
        if (showCart) {
            document.body.style.overflow = 'hidden';
        } else {
            document.body.style.overflow = 'auto';
        }
    }
</script>

<header>
    <div class="pt-4 pb-4 px-2 px-md-5 d-flex justify-content-between align-items-center">
        <!-- svelte-ignore a11y-invalid-attribute -->
        <a href="javascript:void(0)" class="text-dark aside-link" on:click={toggleNavbar}>
            <Icon icon="mdi:hamburger-menu" width="2rem" height="2rem" />
        </a>

        <a href="/" class="fs-4 p-0 m-0 akkurat text-dark header__martinleib">MARTINLEIB</a>

        <!-- svelte-ignore a11y-invalid-attribute -->
        <a href="javascript:void(0)" class="text-dark" on:click={toggleCart}>
            <Icon icon="mdi:cart" width="2rem" height="2rem" />
        </a>
    </div>
</header>

{#if showNavbar}
    <div class="overlay show" on:click={toggleNavbar} transition:fade={{ delay: 200, duration: 300 }}></div>
    <aside class="px-2 px-md-5 aside-container text-white aside-link" transition:fade={{ delay: 200, duration: 300 }}>
        <div class="pt-4 pb-4">
            <a href="javascript:void(0)" on:click={toggleNavbar} class="text-white aside-link">
                <Icon icon="mdi:hamburger-menu" width="2rem" height="2rem" />
            </a>
        </div>
        <nav class="navbar">
            <ul class="list-unstyled">
                <li class="nav-item">
                    <a href="/" class="nav-link text-white aside-link" on:click={toggleNavbar}>Main</a>
                </li>
                <li class="nav-item">
                    <a href="/login/" class="nav-link text-white aside-link" on:click={toggleNavbar}>Your downloads</a>
                </li>
                <li class="nav-item">
                    <a href="/contact/" class="nav-link text-white aside-link" on:click={toggleNavbar}>Contact</a>
                </li>
            </ul>
        </nav>
    </aside>
{/if}

{#if showCart}
    <div class="overlay show" on:click={toggleCart} transition:fade={{ delay: 200, duration: 300 }}></div>
    <aside class="px-md-4 pt-4 cart-container text-white" transition:fade={{ delay: 200, duration: 300 }}>
        <div class="d-flex justify-content-between align-items-center text-center">
            <p class="text-uppercase mb-0">Your Cart</p>
            <a href="javascript:void(0)" on:click={toggleCart} class="text-white">
                <Icon icon="material-symbols:close" />
            </a>
        </div>
        <hr class="cart__hr">
        <div class="cart__items">
            <!-- TODO: implementar código {#if} {#else} -->
            <div class="text-center">
                <p class="mb-0">There are no items in your cart</p>
            </div>
        </div>
    </aside>
{/if}