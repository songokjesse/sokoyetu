
<script>
import "../assets/app.css";
import Navbar from "../components/Navbar.svelte";
import Footer from "../components/Footer.svelte";
</script>

<svelte:head>
  <title>{'Soko Yetu : Eldoret'}</title>
</svelte:head>

<Navbar/>

<main data-theme="light">
  <slot />
</main>

<Footer/>