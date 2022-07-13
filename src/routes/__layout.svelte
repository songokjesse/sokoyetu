<script>
import "../assets/app.css";
import Navbar from "../components/Navbar.svelte";
import Footer from "../components/Footer.svelte";
</script>

<Navbar/>

<main data-theme="light">
  <slot />
</main>

<Footer/>