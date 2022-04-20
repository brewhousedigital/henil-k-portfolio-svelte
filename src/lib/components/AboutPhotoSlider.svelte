<script>
    import photos from "$lib/data/photos.json";
    import '@splidejs/svelte-splide/css';
    import { Splide, SplideSlide } from '@splidejs/svelte-splide';
</script>


<section class="photos">
    <div class="container text-md-start text-center">
        <h2>Outside of work</h2>
        <p>I Love capturing moments and random things while adventuring Hills and traveling historical places.</p>

        <img src="/images/graphics/about-us-photos-border.png" alt="" class="img-fluid photos-border" />
    </div>

    <div class="photos-container">
        <Splide aria-label="My photographs" options={{
        type: "loop",
        drag: "free",
        perPage: 3,
        arrows: false,
        pagination: false,
        autoWidth: true,
    }}>
            {#each photos as {src, alt}}
                <SplideSlide>
                    <img src="/images/photos/{src}" {alt} />
                </SplideSlide>
            {/each}
        </Splide>
    </div>
</section>


<style>
    .photos {
        padding: 80px 0 90px 0;
    }

    .photos h2 {
        color: #999999;
        font-size: 18px;
        line-height: 23px;
        font-weight: 600;
        margin-bottom: 12px;
    }

    .photos p {
        color: #1A1A1A;
        font-size: 22px;
        line-height: 28px;
        font-weight: 600;
        margin-bottom: 16px;
    }

    .photos .photos-border {
        margin-bottom: 48px;
    }

    @media screen and (min-width: 768px) {
        .photos {
            padding: 72px 0;
        }

        .photos h2 {
            font-size: 22px;
            line-height: 36px;
            margin-bottom: 16px;
        }

        .photos p {
            font-size: 32px;
            line-height: 48px;
            margin-bottom: 40px;
        }

        .photos .photos-border {
            margin-bottom: 64px;
        }
    }
</style>