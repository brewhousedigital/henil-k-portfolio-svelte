<script>
    import ContactFooter from "$lib/components/ContactFooter.svelte";
    import HomepageBlockContainer from "$lib/components/HomepageBlocks/HomepageBlockContainer.svelte";
    import AboutPhotoSlider from "$lib/components/AboutPhotoSlider.svelte";
</script>


<section class="intro">
    <div class="container">
        <div class="row align-items-center justify-content-between">
            <div class="col-auto">
                <img src="/images/graphics/about-photo.jpg" alt="Henil Portrait" class="img-fluid" />
            </div>

            <div class="col intro-content">
                <h1>Hi, I’m Henil, Nice to meet you :)</h1>

                <p>I’m a UX/UI designer currently living in India and am currently working as UX/UI designer on freelance basis.</p>

                <p>I specialize in transforming complex challenges into intuitive, simple, and strategic design solutions based on a human-centered approach.</p>

                <p>Moreover, I’ve earned repeated recognition for my strengths in: Visualisation Skill, Research Construction (building the structure of quantitative and qualitative field research), Conducting User Research, Analyzing (research data, problem definition, and ideation), and Making design system.</p>
            </div>
        </div>
    </div>
</section>


<HomepageBlockContainer>
    <AboutPhotoSlider />
</HomepageBlockContainer>


<HomepageBlockContainer customHeight="50vh">
    <ContactFooter />
</HomepageBlockContainer>


<style>
    .intro {
        padding: 40px 0;
        min-height: 100vh;
        background-color: #000;
        color: #fff;
    }

    .intro img {
        border-radius: 24px;
        margin-bottom: 32px;
    }

    .intro-content {
        max-width: 558px;
    }

    .intro h1 {
        font-weight: 500;
        font-size: 22px;
        line-height: 28px;
        margin-bottom: 20px;
    }

    .intro p {
        font-size: 20px;
        line-height: 26px;
        color: #999999;
        margin-bottom: 30px;
    }

    .intro p:last-child {
        margin-bottom: 0;
    }

    @media screen and (min-width: 768px) {
        .intro {
            padding: 72px 0;
        }

        .intro img {
            margin-bottom: 0;
        }

        .intro h1 {
            font-size: 32px;
            line-height: 40px;
        }

        .intro p {
            line-height: 32px;
        }
    }
</style>