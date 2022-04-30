<script>
    import IconArrowRight from "$lib/assets/IconArrowRight.svelte";
    import ServicesMarquee from "$lib/components/HomepageBlocks/ServicesMarquee.svelte";
    import Pulse from "$lib/assets/Pulse.svelte";
    import PaperPlane from "$lib/assets/PaperPlane.svelte";

    export let standalonePage = false;

    let email = "henilpatel0606@gmail.com";
</script>


<section id="contact-footer">
    <div class="container contact-footer-content {standalonePage ? '' : 'text-xl-start'}  text-center">
        <div class="row align-items-center position-relative z-index-1">
            <div class="{standalonePage ? 'col-xl-12 mb-56 content-standalone' : 'col-xl-6'} content">
                <div class="pulse"><Pulse /></div>

                <h2>Sounds Match?</h2>

                <p class="{standalonePage ? 'mx-auto' : ''}">You are in need of fresh start. A renewal. Perhaps an Mindful and Seamless experience of website and mobile application;</p>

                <br>

                <p class="lets-chat {standalonePage ? 'mx-auto mb-0' : ''}">Let’s chat!</p>
            </div>

            <div class="{standalonePage ? 'col-xl-12 block active' : 'col-xl-6'} text-center">
                <a href="mailto:{email}" target="_blank" class="btn-cta outlined {standalonePage ? 'bg-white mb-4' : ''}">
                    <span>{email}</span>
                    <IconArrowRight />
                </a>
                {#if standalonePage}
                    <a href="/" target="_blank" class="ms-md-4 mb-4 btn-cta outlined bg-white">
                        <span>LinkedIn</span>
                        <IconArrowRight />
                    </a>
                {/if}
            </div>
        </div>

        <div class="plane {standalonePage ? 'centered-plane' : ''}">
            <PaperPlane classes="" />
        </div>
    </div>

    <ServicesMarquee standalone={true} />
</section>


<style>
    #contact-footer {
        padding-top: 96px;
    }

    #contact-footer .container {
        max-width: 927px;
    }

    #contact-footer h2 {
        font-weight: 600;
        font-size: 22px;
        line-height: 28px;
        margin-bottom: 16px;
    }

    .contact-footer-content {
        margin-bottom: 96px;
        position: relative;
    }

    .content p {
        font-size: 20px;
        line-height: 28px;
        color: #5F6063;
        font-weight: 600;
    }

    @media screen and (min-width: 1200px) {
        #contact-footer h2 {
            font-size: 32px;
            line-height: 48px;
        }
    }

    .lets-chat {
        margin-bottom: 48px;
    }

    @media screen and (min-width: 1200px) {
        .lets-chat {
            margin-bottom: 0;
        }
    }

    @media screen and (min-width: 1200px) {
        .content p {
            max-width: 430px;
        }

        .content-standalone p {
            max-width: 563px;
        }
    }

    .pulse {
        margin-bottom: 24px;
    }

    .plane {
        position: absolute;
        left: -216px;
        bottom: -115px;
        user-select: none;
        z-index: 0;
    }

    :global(.plane svg) {
        width: 65%;
        height: auto;
    }

    @media screen and (min-width: 400px) {
        .plane {
            bottom: -114px;
            left: -131px;
        }
    }

    @media screen and (min-width: 500px) {
        .plane {
            bottom: -113px;
            left: -82px;
        }
    }

    @media screen and (min-width: 600px) {
        .plane {
            bottom: -152px;
            left: -131px;
        }

        :global(.plane svg) {width: 85%;}
    }

    @media screen and (min-width: 700px) {
        .plane {
            bottom: -147px;
            left: -69px;
        }

        :global(.plane svg) {width: 85%;}
    }

    @media screen and (min-width: 800px) {
        .plane {
            bottom: -142px;
            left: 46px;
        }

        :global(.plane svg) {width: 85%;}
    }

    @media screen and (min-width: 1200px) {
        .plane {
            bottom: -43px;
            left: 130px;
        }

        :global(.plane svg) {width: 100%;}
    }

    .mb-56 {
        margin-bottom: 56px;
    }

    .z-index-1 {z-index: 1;}

    .centered-plane {
        bottom: -22px;
        left: -99px;
    }
</style>