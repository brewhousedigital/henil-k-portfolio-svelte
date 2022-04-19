<script>
    import IconArrowRight from "$lib/assets/IconArrowRight.svelte";
    import ServicesMarquee from "$lib/components/HomepageBlocks/ServicesMarquee.svelte";

    let email = "henilpatel0606@gmail.com";
</script>


<section id="contact-footer">
    <div class="container contact-footer-content">
        <div class="row align-items-center">
            <div class="col-xl-6 content">
                <h2>Sounds Match?</h2>

                <p>You are in need of fresh start. A renewal. Perheps an Mindful and Seamless experience of website and mobile application;</p>

                <p>Let’s chat!</p>
            </div>

            <div class="col-xl-6 text-center">
                <a href="mailto:{email}" target="_blank" class="btn-cta outlined">
                    <span>{email}</span>
                    <IconArrowRight />
                </a>
            </div>
        </div>
    </div>

    <ServicesMarquee />
</section>


<style>
    #contact-footer {
        padding-top: 96px;
    }

    #contact-footer h2 {
        font-weight: 600;
    }

    .contact-footer-content {
        margin-bottom: 96px;
    }

    .content p {
        max-width: 430px;
    }
</style>