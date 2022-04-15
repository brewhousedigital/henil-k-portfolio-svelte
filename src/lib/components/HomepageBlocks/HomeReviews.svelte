<script>
    import listOfReviews from "$lib/data/listOfReviews.json";

    export let visible = false;

    let activeReviewIndex = 0;
    let testimonial = {};
    let testimonialContent = "";
    $: {
        testimonial = listOfReviews[activeReviewIndex];
        testimonialContent = testimonial.content;
    }

    function generateBgCSS(color) {
        return `background-color: ${color};`;
    }
</script>


<section id="reviews" class={visible ? 'active' : ''}>
    <div class="container">
        <h2>Top quality & high results are what I bring to my clients.</h2>

        <div class="d-flex align-items-center justify-content-between">
            <div class="sidebar col-auto">
                {#each listOfReviews as person, index}
                    <button type="button"
                            class="btn d-flex align-items-center {activeReviewIndex === index && 'active'}"
                            on:click={() => {activeReviewIndex = index}}
                            style={activeReviewIndex === index && generateBgCSS(person.bgColor)}>
                        <img src={person.avatar} alt={person.name} class="img-fluid"/>
                        <span class="d-block">
                            <span class="person-name">{person.name}</span>
                            <span class="person-title">{person.title}</span>
                        </span>
                    </button>
                {/each}
            </div>

            <div class="col-auto">
                <img src="/images/divider.png" alt="divider" class="img-fluid d-block" />
            </div>

            <div class="testimonial col" data-highlight={testimonial.bgColor}>
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

    h2 {
        max-width: 558px;
        font-size: 32px;
        line-height: 48px;
        font-weight: 600;
        margin-bottom: 56px;
    }

    .sidebar {
        width: 260px;
    }

    .sidebar button {
        padding: 20px 10px 20px 24px;
        color: #fff;
        text-align: left;
        margin-bottom: 16px;
        border-radius: 15px;
        transition: all 200ms;
    }

    .sidebar button.active {
        box-shadow: 0 12px 24px rgba(15, 91, 85, 0.3);
    }

    .sidebar button img {
        margin-right: 16px;
    }

    .testimonial {
        max-width: 509px;
    }


</style>