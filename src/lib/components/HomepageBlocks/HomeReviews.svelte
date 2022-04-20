<script>
    import listOfReviews from "$lib/data/listOfReviews.json";
    import Quote from "$lib/assets/Quote.svelte";
    import {onMount, afterUpdate} from "svelte";

    export let visible = false;

    let activeReviewIndex = 0;
    let testimonial = {};
    let testimonialContent = "";
    $: {
        testimonial = listOfReviews[activeReviewIndex];
        testimonialContent = testimonial.content;
    }

    afterUpdate(() => {
        $: {
            if(activeReviewIndex === 0) {
                document.querySelector(".btn-0").setAttribute("data-z", "6");
                document.querySelector(".btn-1").setAttribute("data-z", "5");
                document.querySelector(".btn-2").setAttribute("data-z", "4");
            } else if(activeReviewIndex === 1) {
                document.querySelector(".btn-0").setAttribute("data-z", "5");
                document.querySelector(".btn-1").setAttribute("data-z", "6");
                document.querySelector(".btn-2").setAttribute("data-z", "4");
            } else if(activeReviewIndex === 2) {
                document.querySelector(".btn-0").setAttribute("data-z", "4");
                document.querySelector(".btn-1").setAttribute("data-z", "5");
                document.querySelector(".btn-2").setAttribute("data-z", "6");
            }
        }
    })

    function generateBgCSS(color) {
        return `background-color: ${color};`;
    }
</script>


<section id="reviews" class={visible ? 'active' : ''}>
    <div class="container position-relative">
        <div class="quote"><Quote /></div>

        <h2 class="text-md-start text-center">Top quality & high results are what I bring to my clients.</h2>

        <div class="row align-items-center justify-content-between">
            <div class="sidebar clearfix col-lg-auto col-12 order-lg-first order-last">
                {#each listOfReviews as person, index}
                    <button type="button"
                            class="btn btn-{index} d-flex align-items-center {activeReviewIndex === index && 'active'}"
                            on:click={() => {activeReviewIndex = index}}
                            style={activeReviewIndex === index ? generateBgCSS(person.bgColor) : ''}
                            data-z="0">
                        <img src={person.avatar} alt={person.name} class="img-fluid"/>
                        <span class="d-block">
                            <span class="person-name">{person.name}</span>
                            <span class="person-title">{person.title}</span>
                        </span>
                    </button>
                {/each}
            </div>

            <div class="d-lg-block d-none col-auto">
                <img src="/images/divider.png" alt="divider" class="img-fluid d-block" />
            </div>

            <div class="testimonial col-lg col-12 text-md-start text-center" data-highlight={testimonial.bgColor}>
                {@html testimonialContent}
            </div>
        </div>
    </div>
</section>


<style>
    #reviews {
        padding-top: 96px;
    }

    #reviews .container {
        max-width: 934px;
    }

    .quote {
        position: absolute;
        top: -49px;
        left: calc(50% - 28px);
        opacity: 0.3;
    }

    :global(.quote svg) {
        width: 100%;
        max-width: 56px;
    }

    h2 {
        max-width: 558px;
        font-size: 22px;
        line-height: 28px;
        font-weight: 600;
        margin-bottom: 40px;
    }

    .sidebar {
        width: 100%;
        position: relative;
    }

    .sidebar button {
        padding: 16px 10px 16px 16px;
        color: #222;
        text-align: left;
        margin-bottom: 16px;
        border-radius: 15px;
        transition: all 200ms;
        max-width: 250px;
        width: 100%;
        background-color: #F2F2F2;
        border: 2px solid #fff;
        position: absolute;
        top: 0;
        z-index: 3;
    }

    .sidebar button:nth-child(1) {
        left: 16px;
    }

    .sidebar button:nth-child(2) {
        left: calc(50% - 130px);
        max-width: 260px;
    }

    .sidebar button:nth-child(3) {
        right: 16px;
    }

    :global([data-z='4']) {z-index: 4!important;}
    :global([data-z='5']) {z-index: 5!important;}
    :global([data-z='6']) {z-index: 6!important;}

    .sidebar button.active {
        color: #fff;
        border: 2px solid transparent;
        transform: scale(1.1);
        z-index: 4;
    }

    .sidebar button.active:nth-child(1) {
        left: 26px;
    }

    .sidebar button.active:nth-child(3) {
        right: 26px;
    }

    .person-name {
        font-weight: 500;
        font-size: 16px;
        line-height: 24px;
        display: block;
    }

    .person-title {
        display: block;
        font-size: 14px;
        line-height: 24px;
        font-weight: 500;
        opacity: 0.6;
    }

    @media screen and (min-width: 768px) {
        .sidebar {
            width: 290px;
        }

        .sidebar button {
            max-width: 256px;
            padding: 20px 10px 20px 24px;
            color: #fff;
            border: 0;
            position: static;
            background-color: transparent;
        }
    }

    .sidebar button.active {
        box-shadow: 0 12px 24px rgba(15, 91, 85, 0.3);
    }

    .sidebar button img {
        margin-right: 16px;
    }

    .testimonial {
        max-width: 509px;
        font-size: 20px;
        line-height: 32px;
        font-weight: 500;
    }

    @media screen and (min-width: 768px) {
        .quote {
            top: -43px;
            left: -57px;
        }

        :global(.quote svg) {
            width: 100%;
            max-width: 100%;
        }

        h2 {
            font-size: 32px;
            line-height: 48px;
            margin-bottom: 56px;
        }
    }
</style>