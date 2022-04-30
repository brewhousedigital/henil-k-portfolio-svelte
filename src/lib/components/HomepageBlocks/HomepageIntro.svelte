<script>
    import IconArrowRight from "$lib/assets/IconArrowRight.svelte";
    import HomepageIntroArrows from "$lib/assets/HomepageIntroArrows.svelte";
</script>


<section id="intro">
    <div class="container">
         <div class="row g-0">
             <div class="col content">
                 <h2>Hi, I'm Henil</h2>
                 <p>A self-taught UX/UI designer. I create mindful and seamless user experiences that communicate via beautiful interfaces from concept to completion.</p>

                 <div>
                     <a href="/" class="btn-cta no-bg" sveltekit:prefetch>
                         <span>Let's work together</span>
                         <IconArrowRight />
                     </a>
                 </div>
             </div>
             <div class="col-auto d-lg-block d-none">
                <img src="/images/graphics/homepage-intro-bulb.svg" alt="" class="img-fluid" />
             </div>
         </div>
    </div>

    <div class="intro-arrows"><HomepageIntroArrows /></div>
</section>


<style>
    #intro {
        position: relative;
        min-height: calc(100vh - 100px);
        background-color: #000;
        padding-top: 108px;
    }

    #intro .content {
        width: 100%;
        max-width: 703px;
        color: #fff;
    }

    .intro-arrows {
        position: absolute;
        bottom: 40px;
        left: calc(50% - 20px);
        animation-name: introArrowsAnimation;
        animation-direction: alternate;
        animation-iteration-count: infinite;
        animation-duration: 1s;
        animation-timing-function: linear;
    }

    @keyframes introArrowsAnimation {
        0% {transform: translateY(0px)}
        100% {transform: translateY(15px)}
    }

    #intro h2 {
        color: #787C84;
        font-weight: 600;
        font-size: 18px;
        line-height: 24px;
        margin-bottom: 16px;
    }

    #intro p {
        font-weight: 500;
        font-size: 24px;
        line-height: 32px;
        margin-bottom: 48px;
    }

    #intro .cta span {
        display: inline-block;
        margin-right: 18px
    }

    @media screen and (min-width: 768px) {
        #intro h2 {
            font-size: 24px;
            line-height: 30px;
            margin-bottom: 24px;
        }

        #intro p {
            font-weight: 500;
            font-size: 32px;
            line-height: 40px;
            margin-bottom: 72px;
        }
    }
</style>