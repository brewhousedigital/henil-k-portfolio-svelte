<script>
    import VisibilityContainer from "$lib/components/VisibilityContainer.svelte";

    export let customHeight = "";
    let styles = "";

    $: customHeight ? styles = `min-height: ${customHeight};` : "";

</script>


<VisibilityContainer steps={100} let:percent>
    <div class="block {percent > 70 ? 'active' : ''}" style={styles}>
        <slot></slot>
    </div>
</VisibilityContainer>


<style>
    .block {
        min-height: 100vh;
        background-color: #000;
        color: #fff;
        transition: all 2000ms;
    }

    .block.active {
        background-color: #fff;
        color: #050505;
    }
</style>