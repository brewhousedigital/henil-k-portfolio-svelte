<script>
    import listOfCaseStudies from "$lib/data/listOfCaseStudies.json";
    import CaseStudy from "$lib/components/CaseStudy.svelte";
    import ContactFooter from "$lib/components/ContactFooter.svelte";
    import HomepageBlockContainer from "$lib/components/HomepageBlocks/HomepageBlockContainer.svelte";
</script>


<div class="container block active">
    <h1 class="text-center">Outcomes that brings value</h1>
    {#each listOfCaseStudies as item, index}
        <div class="case-study">
            <CaseStudy {index}
                       tag={item.tag}
                       standalone={true}
                       reverse={index === 1}
                       title={item.title}
                       content={item.content}
                       href={item.href}
                       src={item.src}
                       ctaColor={item.ctaColor}
            />
        </div>
    {/each}
</div>

<HomepageBlockContainer customHeight="50vh">
    <ContactFooter />
</HomepageBlockContainer>


<style>
    h1 {
        font-size: 32px;
        font-weight: 600;
        line-height: 48px;
        color: #050505;
        margin-bottom: 72px;
        padding-top: 64px;
    }

    @media screen and (max-width: 768px) {
        .case-study {
            padding: 0 4px;
        }
    }

    @media screen and (min-width: 768px) {
        .case-study {
            margin-bottom: 120px;
        }
    }
</style>