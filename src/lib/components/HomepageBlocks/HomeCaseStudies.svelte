<script>
    import IconArrowRight from "$lib/assets/IconArrowRight.svelte";
    import listOfCaseStudies from "$lib/data/listOfCaseStudies.json";
    import CaseStudy from "$lib/components/CaseStudy.svelte";

    export let visible = false;
</script>

<section id="case-studies" class={visible ? 'active' : ''}>
    <div class="case-study-header">
        <div class="container d-flex align-items-center justify-content-between">
            <h2>Outcomes that brings value</h2>
            <a class="btn-cta slim">
                <span>See All Projects</span>
                <IconArrowRight />
            </a>
        </div>
    </div>


    <div class="container">
        {#each listOfCaseStudies as item, index}
            <CaseStudy {index}
                       tag={item.tag}
                       title={item.title}
                       content={item.content}
                       href={item.href}
                       src={item.src}
            />
        {/each}
    </div>
</section>


<style>
    .case-study-header {
        padding: 24px 0;
        border-bottom: 2px solid #fff;
        margin-bottom: 76px;
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
</style>