<script lang="ts">
  import { base } from "$app/paths";
  import { onMount } from "svelte";

  let initScroll = $state(0);
  let bg_opacity = 0.9;

  onMount(() => {});
</script>

<svelte:window bind:scrollY={initScroll} />

<main
  class="mx-auto max-w-4xl w-full flex"
  style="background: linear-gradient(rgba(255, 255, 255, {bg_opacity}), rgba(255, 255, 255, {bg_opacity})), url('{base}/0.png'); background-size: contain;"
>
  <div class="h-[200vh]"></div>
</main>
