<script>
    import { fade } from 'svelte/transition';

    export let icon = "";
    export let bgColor = "";
    export let hoverContent = "";
    export let title = "";
    export let content = "";

    let src = `/images/icons/${icon}-icon.png`;
    let hoverCSS = `background-color: ${bgColor}`;

    let isHovering = false;

    function handleMouseEnter() {
        isHovering = true;
    }

    function handleMouseLeave() {
        isHovering = false;
    }
</script>


<div class="block" on:mouseenter={handleMouseEnter} on:mouseleave={handleMouseLeave}>
    <div class="icon">
        <img {src} alt="" class="img-fluid" />
    </div>

    <h3>{title}</h3>
    <p>{content}</p>

    {#if isHovering}
        <div class="hover" style={hoverCSS} transition:fade={{duration: 200}}>
            {hoverContent}
        </div>
    {/if}
</div>


<style>
    .block {
        position: relative;
        max-width: 430px;
        height: 100%;
        min-height: 204px;
        cursor: help;
        margin: 0 auto;
    }

    .hover {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background-color: #222;
        border-radius: 16px;
        box-shadow: 0 0 24px rgba(15, 91, 85, 0.24);
        padding: 24px 12px;
        font-size: 18px;
        line-height: 28px;
        color: #F2F2F2;
    }

    .icon {
        margin-bottom: 18px;
    }

    h3 {
        font-weight: 500;
        font-size: 22px;
        line-height: 32px;
        margin-bottom: 4px;
    }

    p {
        font-size: 20px;
        line-height: 26px;
        max-width: 397px;
        margin: 0 auto;
    }

    @media screen and (min-width: 768px) {
        h3 {
            font-size: 28px;
            line-height: 40px;
        }

        p {
            font-size: 24px;
            line-height: 36px;
        }

        .hover {
            font-size: 24px;
            line-height: 31px;
        }
    }
</style>