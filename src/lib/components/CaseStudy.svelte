<script>
    import IconArrowRight from "$lib/assets/IconArrowRight.svelte";

    export let index = 1;
    export let tag = "";
    export let title = "";
    export let content = "";
    export let href = "";
    export let src = "";
    export let ctaColor = "";
    export let standalone = false;
    export let reverse = false;

    function prettyIndex(index) {
        let increment = index + 1;
        let string = String(increment);
        return string.length === 1
            ? "0" + string
            : string;
    }
</script>

<div class="case-study-container {standalone ? 'p-0' : ''}">
<div class="row g-0 align-items-center">
    <div class="col-lg-6 {reverse ? 'ps-121' : 'order-lg-first pe-121'} order-last">
        <div class="content">
            <div class="tag">
                <span>{prettyIndex(index)}// </span>{tag}
            </div>

            <h3>{title}</h3>
            <p class="d-md-block d-none">{content}</p>

            <div>
                <a {href} class="btn-cta btn-cta-{ctaColor}" sveltekit:prefetch>
                    <span>View Case</span>
                    <IconArrowRight />
                </a>
            </div>
        </div>
    </div>

    <div class="col-lg-6">
        <img {src} alt="Case Study example of {title}" class="img-fluid" />
    </div>
</div>
</div>


<style>
    .case-study-container{
        padding: 0 4px;
    }

    .ps-121 {padding-left: 121px}
    .pe-121 {padding-right: 121px}

    @media screen and (min-width: 768px) {
        .case-study-container{
            padding: 0 80px;
        }
    }

    .content {
        max-width: 461px;
        margin-bottom: 56px;
    }

    @media screen and (min-width: 768px) {
        .content {
            margin-bottom: 0;
        }
    }

    .tag {
        color: #999999;
        font-size: 16px;
        line-height: 30px;
        font-weight: 500;
        margin-bottom: 8px;
    }

    .tag span {
        color: #1A1A1A;
    }

    .content h3 {
        font-weight: 600;
        font-size: 20px;
        line-height: 28px;
        margin-bottom: 16px;
    }

    .content p {
        font-size: 20px;
        color: #999999;
        line-height: 32px;
        margin-bottom: 32px;
    }

    img {
        margin-bottom: 16px;
    }



    @media screen and (min-width: 768px) {
        .tag {
            font-size: 18px;
        }

        .content h3 {
            font-size: 32px;
            line-height: 42px;
            margin-bottom: 24px;
        }

        img {
            margin-bottom: 0;
        }
    }
</style>