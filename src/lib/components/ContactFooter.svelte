<script>
    import IconArrowRight from "$lib/assets/IconArrowRight.svelte";
    import ServicesMarquee from "$lib/components/HomepageBlocks/ServicesMarquee.svelte";
    import Pulse from "$lib/assets/Pulse.svelte";
    import PaperPlane from "$lib/assets/PaperPlane.svelte";

    let email = "henilpatel0606@gmail.com";
</script>


<section id="contact-footer">
    <div class="container contact-footer-content text-lg-start text-center">
        <div class="row align-items-center">
            <div class="col-xl-6 content">
                <div class="pulse"><Pulse /></div>

                <h2>Sounds Match?</h2>

                <p>You are in need of fresh start. A renewal. Perheps an Mindful and Seamless experience of website and mobile application;</p>

                <br>

                <p class="lets-chat">Let’s chat!</p>
            </div>

            <div class="col-xl-6 text-center">
                <a href="mailto:{email}" target="_blank" class="btn-cta outlined">
                    <span>{email}</span>
                    <IconArrowRight />
                </a>
            </div>
        </div>

        <div class="plane">
            <PaperPlane classes="" />
        </div>
    </div>

    <ServicesMarquee />
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
        max-width: 430px;
        font-size: 20px;
        line-height: 28px;
    }

    .lets-chat {
        margin-bottom: 48px;
    }

    @media screen and (min-width: 768px) {
        .lets-chat {
            margin-bottom: 0;
        }
    }

    .pulse {
        margin-bottom: 24px;
    }

    .plane {
        position: absolute;
        left: -216px;
        bottom: -115px;
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
</style>