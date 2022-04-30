<script>
    import '@splidejs/splide/css';
    import { Splide, SplideSlide } from '@splidejs/svelte-splide';

    import IconArrowRight from "$lib/assets/IconArrowRight.svelte";
    import listOfCaseStudies from "$lib/data/listOfCaseStudies.json";
    import CaseStudy from "$lib/components/CaseStudy.svelte";

    export let visible = false;
</script>

<section id="case-studies" class={visible ? 'active' : ''}>
    <div class="case-study-header">
        <div class="container d-flex align-items-center justify-content-between">
            <h2 class="text-lg-start text-center col-lg-auto col">Outcomes that brings value</h2>
            <a class="btn-cta no-bg slim d-lg-block d-none">
                <span>See All Projects</span>
                <IconArrowRight />
            </a>
        </div>
    </div>


    <div class="container">
        <div class="d-md-block d-none">
            <Splide aria-label="My Case Studies" options={{type: 'loop', pagination: false}}>
                {#each listOfCaseStudies as item, index}
                    <SplideSlide>
                        <CaseStudy {index}
                                   tag={item.tag}
                                   title={item.title}
                                   content={item.content}
                                   href={item.href}
                                   src={item.src}
                                   ctaColor={item.ctaColor}
                        />
                    </SplideSlide>
                {/each}
            </Splide>
        </div>

        <div class="d-md-none d-block">
            {#each listOfCaseStudies as item, index}
                <CaseStudy {index}
                           tag={item.tag}
                           title={item.title}
                           content={item.content}
                           href={item.href}
                           src={item.src}
                           ctaColor={item.ctaColor}
                />
            {/each}
        </div>
    </div>

    <div class="see-all-projects-mobile position-sticky d-md-none d-flex align-items-center justify-content-center">
        <span>See All Projects</span>
        <IconArrowRight />
    </div>
</section>


<style>
    .case-study-header {
        padding: 24px 0;
        border-bottom: 2px solid #000;
        margin-bottom: 76px;
    }

    @media screen and (min-width: 768px){
        .case-study-header {
            border-bottom-color: #fff;
        }
    }

    .case-study-header h2 {
        font-size: 24px;
        line-height: 30px;
        font-weight: 600;
        margin: 0;
    }

    .case-study-header p {
        font-size: 18px;
        font-weight: 600;
        line-height: 30px;
        margin: 0;
    }

    .case-study-header p span {
        margin-right: 24px;
        display: inline-block;
    }

    .see-all-projects-mobile {
        background-color: rgba(255, 255, 255, 0.9);
        backdrop-filter: blur(10px);
        bottom: 0;
        border-top: 2px solid #000;
    }

    .see-all-projects-mobile span {
        font-size: 18px;
        line-height: 30px;
        font-weight: 600;
        padding: 13px 0;
        display: block;
        margin-right: 24px;
    }

    :global(.see-all-projects-mobile svg path) {
        fill: #000;
    }
</style>