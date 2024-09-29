<script>
  import { PUBLIC_COMPANY_NAME } from "$env/static/public";
  import Footer from "$lib/Footer.svelte";
  import Header from "$lib/Header.svelte";
  import "../app.css";
</script>

<svelte:head>
    <title> {PUBLIC_COMPANY_NAME}</title> 
</svelte:head>


<div class="h-screen flex flex-col justify-between">
  <Header /> 
  <main class="h-full mt-16">
    <slot />
  </main>
  <Footer />
</div>
