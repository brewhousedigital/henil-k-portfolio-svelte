<script>
    import links from "$lib/data/navLinks.json";
    import LogoWhite from "$lib/assets/LogoWhite.svelte";
    import MenuIcon from "$lib/assets/MenuIcon.svelte";
    import MobileNavDrawer from "$lib/components/MobileNavDrawer.svelte";


    let mobileNav = false;
</script>


<header>
    <div class="container d-flex align-items-center justify-content-between">
        <a href="/" class="logo" sveltekit:prefetch>
            <LogoWhite />
        </a>

        <nav class="d-lg-block d-none">
            {#each links as {text, href}}
                <a {href} sveltekit:prefetch>{text}</a>
            {/each}
        </nav>

        <button type="button" class="d-lg-none d-block btn header-btn" on:click={() => {mobileNav = true}}>
            <MenuIcon />
        </button>
    </div>
</header>


<MobileNavDrawer bind:show={mobileNav} />


<style>
    header {
        background-color: #000;
        padding: 24px 16px;
    }

    .logo {
        color: #fff;
        font-weight: 700;
        font-size: 30px;
        text-decoration: none;
    }

    nav a {
        display: inline-block;
        padding: 10px 20px;
        text-decoration: none;
        font-weight: 500;
        color: #787C84;
    }

    .header-btn {
        color: #fff;
        padding: 5px;
    }

    @media screen and (min-width: 768px) {
        header {
            padding: 0;
        }
        .container {
            height: 100px;
        }
    }
</style>