<script context="module">
  export const load = ({ page }) => {
    const path = page.path;
    console.log(page);
    return {
      props: {
        path,
      },
    };
  };
</script>

<script>
  import Nav from "$lib/Nav.svelte";
  export let path;
  import { fly } from "svelte/transition";
</script>

<Nav {path} />
<div
  in:fly={{ y: -50, duration: 250, delay: 300 }}
  out:fly={{ y: -50, duration: 250 }}
  class="container"
>
  <slot />
</div>

<style>
  .container {
    background-color: #181820;
    display: flex;
    flex-direction: column;
    height: 100%;
  }
</style>
