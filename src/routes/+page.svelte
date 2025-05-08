<script lang="ts">
  import { base } from "$app/paths";
  import { onMount } from "svelte";

  let initScroll = $state(0);
  let bg_opacity = 0.95;

  onMount(() => {});
</script>

<svelte:window bind:scrollY={initScroll} />

{#snippet entry()}
  <div class="flex">lakjdf</div>
{/snippet}

<main
  class="mx-auto max-w-4xl w-full flex aspect-[9/16] overflow-hidden"
  style="background: linear-gradient(rgba(255, 255, 255, {bg_opacity}), rgba(255, 255, 255, {bg_opacity})), url('{base}/0.png'); background-size: contain;"
>
  <div class="grid grid-cols-2 w-full relative">
    <div
      class="bg-[var(--timeline-line-color)] rounded-t-sm mt-64 w-3 h-full absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2"
    >
      <!-- middle bar -->
    </div>

    <p>ldkjfsf</p>
    <p>ldkjfsf</p>

  </div>
</main>
