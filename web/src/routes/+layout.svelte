<script>
  import Footer from "$lib/Footer.svelte";
  import Header from "$lib/Header.svelte";
  import "../app.css";
</script>

<svelte:head>
  <title>app name here</title>
</svelte:head>

<div class="h-screen flex flex-col justify-between">
  <Header /> 
  <main class="h-full mt-16">
    <slot />
  </main>
  <Footer />
</div>
