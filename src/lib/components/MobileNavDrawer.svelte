<script>
    import {afterUpdate} from "svelte";
    import { slide } from 'svelte/transition';
    import links from "$lib/data/navLinks.json";

    import LogoBlack from "$lib/assets/LogoBlack.svelte";

    export let show = false;

    afterUpdate(() => {
        $: {
            if(show) {
                document.querySelector("body").style.overflow = "hidden";
            } else {
                document.querySelector("body").style.overflow = "";
            }
        }
    });

    function handleClose() {
        show = false;
    }
</script>


{#if show}
    <div class="mobile-nav-drawer d-flex flex-column" transition:slide>
        <div class="col-auto">
            <div class="header d-flex align-items-center justify-content-between">
                <div>
                    <a href="/" class="logo" sveltekit:prefetch on:click={handleClose}>
                        <LogoBlack />
                    </a>
                </div>

                <button type="button" class="btn" on:click={handleClose}>
                    <img src="/images/icons/icon-close.png" alt="close" class="img-fluid" />
                </button>
            </div>
        </div>

        <div class="col text-center">
            <div class="content">
                {#each links as {text, href}}
                    <a {href} sveltekit:prefetch on:click={handleClose}>{text}</a>
                {/each}
            </div>
        </div>

        <div class="col-auto text-center">
            <button type="button" class="btn footer-btn" on:click={handleClose}>
                <img src="/images/icons/icon-close-grey.png" alt="close" class="img-fluid" />
                <span>Close</span>
            </button>
        </div>
    </div>
{/if}


<style>
    .mobile-nav-drawer {
        background-color: #fff;
        position: fixed;
        z-index: 5;
        top: 0;
        left: 0;
        height: 100vh;
        width: 100vw;
    }

    .header {
        padding: 24px;
    }

    .content {
        height: 100%;
        display: flex;
        align-items: center;
        justify-content: center;
        flex-direction: column;
    }

    .content a {
        display: block;
        font-weight: 600;
        font-size: 22px;
        line-height: 36px;
        padding: 12px 0;
        color: #000 ;
        text-decoration: none;
    }

    .footer-btn {
        display: flex;
        justify-content: center;
        align-items: center;
        width: 100%;
    }

    .footer-btn span {
        font-weight: 500;
        font-size: 20px;
        line-height: 36px;
        margin-left: 8px;
        color: #4C4C4C;
    }
</style>