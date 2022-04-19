<script>
    import IconArrowRight from "$lib/assets/IconArrowRight.svelte";

    export let index = 1;
    export let tag = "";
    export let title = "";
    export let content = "";
    export let href = "";
    export let src = "";

    function prettyIndex(index) {
        let increment = index + 1;
        let string = String(increment);
        return string.length === 1
            ? "0" + string
            : string;
    }
</script>

<div class="case-study-container">
<div class="row align-items-center">
    <div class="col-lg-6">
        <div class="content">
            <div class="tag">
                <span>{prettyIndex(index)}// </span>{tag}
            </div>

            <h3>{title}</h3>
            <p>{content}</p>

            <div>
                <a {href} class="btn-cta" sveltekit:prefetch>
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
        padding: 0 80px;
    }
    .content {
        max-width: 461px;
    }

    .tag {
        color: #999999;
        font-size: 18px;
        line-height: 30px;
        font-weight: 500;
        margin-bottom: 8px;
    }

    .tag span {
        color: #1A1A1A;
    }

    .content h3 {
        font-weight: 600;
        font-size: 32px;
        line-height: 42px;
        margin-bottom: 24px;
    }

    .content p {
        font-size: 20px;
        color: #999999;
        line-height: 32px;
        margin-bottom: 32px;
    }
</style>