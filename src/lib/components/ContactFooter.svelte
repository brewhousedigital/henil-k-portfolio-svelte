<script>
    import IconArrowRight from "$lib/assets/IconArrowRight.svelte";
    import ServicesMarquee from "$lib/components/HomepageBlocks/ServicesMarquee.svelte";
    import Pulse from "$lib/assets/Pulse.svelte";
    import PaperPlane from "$lib/assets/PaperPlane.svelte";

    let email = "henilpatel0606@gmail.com";
</script>


<section id="contact-footer">
    <div class="container contact-footer-content">
        <div class="row align-items-center">
            <div class="col-xl-6 content">
                <div class="pulse"><Pulse /></div>

                <h2>Sounds Match?</h2>

                <p>You are in need of fresh start. A renewal. Perheps an Mindful and Seamless experience of website and mobile application;</p>

                <br>

                <p>Let’s chat!</p>
            </div>

            <div class="col-xl-6 text-center">
                <a href="mailto:{email}" target="_blank" class="btn-cta outlined">
                    <span>{email}</span>
                    <IconArrowRight />
                </a>
            </div>
        </div>

        <div class="plane"><PaperPlane /></div>
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
        margin-bottom: 16px;
    }

    .contact-footer-content {
        margin-bottom: 96px;
        position: relative;
    }

    .content p {
        max-width: 430px;
    }

    .pulse {
        margin-bottom: 24px;
    }

    .plane {
        position: absolute;
        bottom: -43px;
        width: 100%;
        left: 130px;
    }
</style>