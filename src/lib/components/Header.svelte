<script>
    let links = [
        {text: "About", href: "/about"},
        {text: "Works", href: "/works"},
        {text: "Resume", href: "/resume"},
        {text: "Contact", href: "/contact"},
    ]
</script>


<header>
    <div class="container d-flex align-items-center justify-content-between">
        <a href="/" class="logo" sveltekit:prefetch>
            HK
        </a>

        <nav>
            {#each links as {text, href}}
                <a {href} sveltekit:prefetch>{text}</a>
            {/each}
        </nav>
    </div>
</header>


<style>
    header {
        background-color: #000;
    }

    .container {
        height: 100px;
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
</style>