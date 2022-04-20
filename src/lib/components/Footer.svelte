<script>
    import LogoWhite from "$lib/assets/LogoWhite.svelte";
</script>


<footer>
    <div class="container text-md-start text-center">
        <div class="row">
            <div class="col-md col-12">
                <div class="logo">
                    <LogoWhite />
                </div>

                <p class="d-md-block d-none">© 2022 Henil Kajavadra</p>
            </div>

            <div class="col">
                <h2 class="d-md-block d-none">Social</h2>

                <nav class="d-md-block d-flex justify-content-around">
                    <a href="" target="_blank">LinkedIn</a>
                    <a href="" target="_blank">Dribbble</a>
                    <a href="" target="_blank">Behance</a>
                </nav>
            </div>

            <div class="col d-md-block d-none">
                <h2>Navigation</h2>

                <nav>
                    <a href="" sveltekit:prefetch>About</a>
                    <a href="" sveltekit:prefetch>Works</a>
                    <a href="" sveltekit:prefetch>Contact</a>
                </nav>
            </div>

            <div class="col d-md-block d-none">
                <div class="scroll-text">Ohh! Scrolling never ends, <br>Try to scroll :) </div>
            </div>
        </div>

        <p class="secondary-copyright d-md-none d-block">© 2022 Henil Kajavadra</p>
    </div>
</footer>


<style>
    footer {
        background-color: #000;
        color: #fff;
        padding: 82px 0 96px 0;
    }

    footer h2 {
        font-size: 22px;
        line-height: 36px;
        margin-bottom: 8px;
    }

    footer a {
        color: #fff;
        text-decoration: none;
    }

    footer nav a {
        display: block;
        font-size: 18px;
        line-height: 30px;
        margin-bottom: 8px;
    }

    .scroll-text {
        font-size: 28px;
        line-height: 40px;
        color: #1A1A1A;
        font-weight: 600;
    }

    .logo {
        margin-bottom: 24px;
    }

    footer .row {
        margin-bottom: 32px;
    }

    .secondary-copyright {
        color: #787C84;
        font-size: 16px;
        line-height: 30px;
    }

    @media screen and (min-width: 768px) {
        footer .row {
            margin-bottom: 0;
        }
    }
</style>