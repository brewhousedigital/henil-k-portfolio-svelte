<script>
    import "$lib/assets/global.css";
    import Header from "../lib/components/Header.svelte";
    import Footer from "$lib/components/Footer.svelte";
</script>

<Header />

<slot></slot>

<Footer />