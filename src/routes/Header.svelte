<script>
    import { fade } from 'svelte/transition';
    import Icon from "@iconify/svelte";

    let showNavbar = false;

    function toggleNavbar() {
        showNavbar = !showNavbar;
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
        <a href="javascript:void(0)" class="text-dark">
            <Icon icon="mdi:cart" width="2rem" height="2rem" />
        </a>
    </div>
</header>

{#if showNavbar}
    <aside class="z-1 px-2 px-md-5 aside-container text-white aside-link" transition:fade={{ delay: 200, duration: 300 }}>
        <div class="pt-4 pb-4">
            <!-- svelte-ignore a11y-invalid-attribute -->
            <a href="javascript:void(0)" on:click={toggleNavbar} class="text-white aside-link">
                <Icon icon="mdi:hamburger-menu" width="2rem" height="2rem" />
            </a>
        </div>
        <nav class="navbar">
            <ul class="list-unstyled">
                <li class="nav-item">
                    <a href="/" class="nav-link text-white aside-link">Main</a>
                </li>
                <li class="nav-item">
                    <a href="/login" class="nav-link text-white aside-link">Your downloads</a>
                </li>
                <li class="nav-item">
                    <a href="/contact" class="nav-link text-white aside-link">Contact</a>
                </li>
            </ul>
        </nav>
    </aside>
{/if}
