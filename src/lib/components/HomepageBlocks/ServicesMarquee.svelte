<script>
    import Marquee3k from 'marquee3000';
    import {onMount} from "svelte";

    export let standalone = false;

    onMount(() => {
        Marquee3k.init();

        setTimeout(() => {
            Marquee3k.refreshAll();
        }, 3000)
    })
</script>


<div class="marquee-wrapper {standalone ? 'active' : ''}">
    <div class="marquee-border"><img src="/images/marquee/marquee-border.png" alt="border" class="img-fluid" /></div>

    <div class="marquee">
        <div class="marquee-gradient-1"></div>

        <div class="marquee3k" data-speed="1">
            <div>
                <div class="marquee-container">
                    <div class="marquee-text marquee-text-1C2334">Usability Testing</div>
                    <div class="marquee-text marquee-text-0F5B55">UX Design</div>
                    <div class="marquee-text marquee-text-312651">Visual Design</div>
                    <div class="marquee-text marquee-text-C44E6B">UX Research</div>
                    <div class="marquee-text marquee-text-EABA00">Information Architecture</div>

                    <!--<img src="/images/marquee/Usability Testing-min.png"
                         alt="Usability Testing"
                         class="img-fluid"
                         width="388"
                         height="46" />
                    <img src="/images/marquee/UX Design-min.png"
                         alt="UX Design"
                         class="img-fluid"
                         width="241"
                         height="46" />
                    <img src="/images/marquee/Visual Design-min.png"
                         alt="Visual Design"
                         class="img-fluid"
                         width="317"
                         height="46" />
                    <img src="/images/marquee/UX Research-min.png"
                         alt="UX Research"
                         class="img-fluid"
                         width="298"
                         height="36" />
                    <img src="/images/marquee/Information Architecture-min.png"
                         alt="Information Architecture"
                         class="img-fluid"
                         width="577"
                         height="37" />-->
                </div>
            </div>
        </div>

        <div class="marquee-gradient-2"></div>
    </div>

    <div class="marquee-border"><img src="/images/marquee/marquee-border.png" alt="border" class="img-fluid" /></div>
</div>


<style>
    .marquee-wrapper {
        opacity: 0;
        transition: all 1000ms;
        transition-delay: 1000ms;
    }

    .marquee-wrapper.active {
        opacity: 1;
    }

    .marquee {
        padding: 40px 0;
        margin: 0 auto;
        width: 95vw;
        overflow: hidden;
        position: relative;
        user-select: none;
    }

    .marquee-border img {
        display: block;
        margin: 0 auto;
    }

    .marquee-gradient-1, .marquee-gradient-2 {
        position: absolute;
        top: 0;
        height: 100%;
        width: 100px;
        z-index: 50;
    }

    .marquee-gradient-1 {
        left: 0;
        background: linear-gradient(to right, rgba(255,255,255,1) 0%,rgba(255,255,255,0) 100%);
    }

    .marquee-gradient-2 {
        right: 0;
        background: linear-gradient(to left, rgba(255,255,255,1) 0%,rgba(255,255,255,0) 100%);
    }

    .marquee-container {
        /*width: 2041px;*/
        display: flex;
        align-items: center;
    }

    .marquee-text {
        margin: 0 20px;
        font-weight: 600;
        font-size: 32px;
        line-height: 48px;
        text-shadow: 0 0 3px #000, 0 0 3px #000;
        color: #fff;
    }

    .marquee-text-1C2334 {text-shadow: 0 0 2px #1C2334, 0 0 2px #1C2334, 0 0 2px #1C2334;}
    .marquee-text-0F5B55 {text-shadow: 0 0 2px #0F5B55, 0 0 2px #0F5B55, 0 0 2px #0F5B55;}
    .marquee-text-312651 {text-shadow: 0 0 2px #312651, 0 0 2px #312651, 0 0 2px #312651;}
    .marquee-text-C44E6B {text-shadow: 0 0 2px #C44E6B, 0 0 2px #C44E6B, 0 0 2px #C44E6B;}
    .marquee-text-EABA00 {text-shadow: 0 0 2px #EABA00, 0 0 2px #EABA00, 0 0 2px #EABA00;}

    @media screen and (min-width: 768px) {
        .marquee-text {
            font-size: 48px;
            line-height: 48px;
        }
    }
</style>