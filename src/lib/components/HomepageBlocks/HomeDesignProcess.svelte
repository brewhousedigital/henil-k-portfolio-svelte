<script>
    import listOfDesignBlocks from "$lib/data/listOfDesignBlocks.json";
    import DesignProcessBlock from "$lib/components/DesignProcessBlock.svelte";

    export let visible = false;
</script>


<section id="design-process" class={visible ? 'active' : ''}>
    <div class="container">
        <h2>A better design process</h2>
        <p>I can help you better understand user needs and increase the quality of every digital product.</p>

        <div class="row">
            {#each listOfDesignBlocks as block}
                <div class="col-lg-6 design-block">
                    <DesignProcessBlock icon={block.icon}
                                        bgColor={block.bgColor}
                                        hoverContent={block.hoverContent}
                                        title={block.title}
                                        content={block.content}
                    />
                </div>
            {/each}
        </div>
    </div>
</section>


<style>
    #design-process {
        padding-top: 96px;
        text-align: center;
    }

    #design-process .container {
        max-width: 934px;
    }

    h2 {
        color: #787C84;
        font-weight: 600;
        font-size: 18px;
        line-height: 24px;
        margin-bottom: 12px;
    }

    p {
        font-size: 22px;
        line-height: 28px;
        font-weight: 600;
        max-width: 934px;
        margin: 0 auto 40px auto;
    }

    .design-block {
        margin-bottom: 56px;
    }

    @media screen and (min-width: 768px) {
        h2 {
            font-size: 22px;
            line-height: 36px;
            margin-bottom: 16px;
        }

        p {
            font-size: 32px;
            line-height: 48px;
            margin: 0 auto 96px auto;
        }
    }
</style>