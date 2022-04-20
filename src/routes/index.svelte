<script>
    import HomepageIntro from "$lib/components/HomepageBlocks/HomepageIntro.svelte";
    import HomeDesignProcess from "$lib/components/HomepageBlocks/HomeDesignProcess.svelte";
    import HomeCaseStudies from "$lib/components/HomepageBlocks/HomeCaseStudies.svelte";
    import HomeReviews from "$lib/components/HomepageBlocks/HomeReviews.svelte";
    import HomepageBlockContainer from "$lib/components/HomepageBlocks/HomepageBlockContainer.svelte";
    import ContactFooter from "$lib/components/ContactFooter.svelte";
</script>


<HomepageIntro/>


<HomepageBlockContainer>
    <HomeCaseStudies />
</HomepageBlockContainer>


<HomepageBlockContainer>
    <HomeDesignProcess />
</HomepageBlockContainer>


<HomepageBlockContainer customHeight="68vh">
    <HomeReviews />
</HomepageBlockContainer>


<HomepageBlockContainer customHeight="50vh">
    <ContactFooter />
</HomepageBlockContainer>