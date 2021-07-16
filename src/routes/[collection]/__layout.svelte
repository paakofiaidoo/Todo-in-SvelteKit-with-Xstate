<script context="module">
  export const load = ({ page }) => {
    const path = page.path;
    return {
      props: {
        path,
      },
    };
  };
</script>

<script>
  import { v4 as uuidv4 } from "uuid";
  import Nav from "$lib/Nav.svelte";
  export let path;
  let collections = [
    {
      id: uuidv4(),
      title: "School Todo List",
      icon: "https://img.icons8.com/material-outlined/50/ffffff/school.png",
      todos: [
        {
          title: "learn svelte",
          isComplete: false,
          id: uuidv4(),
        },
      ],
    },
    {
      id: uuidv4(),
      title: "dev Todo List",
      icon: "https://img.icons8.com/material-outlined/50/ffffff/computer.png",
      todos: [
        {
          title: "learn svelte",
          isComplete: false,
          id: uuidv4(),
        },
      ],
    },
  ];
  import { fly } from "svelte/transition";
</script>

<Nav {path} />
<div
  in:fly={{ y: -50, duration: 250, delay: 300 }}
  out:fly={{ y: -50, duration: 250 }}
  class="container"
>
  <main class="main">
    <div class="sideMenu">
      <h4>Collections</h4>
      {#each collections as { title, icon, id }}
        <li class="menuItem">
          <img class="icon" src={icon} alt={title} />
          <a href={`/${id}`}>{title}</a>
        </li>
      {/each}
    </div>
    <slot />
  </main>
</div>

<style>
  .container {
    background-color: #181820;
    display: flex;
    flex-direction: column;
    height: 100%;
  }
  .main {
    width: auto;
    height: 100%;
    width: 100%;
    display: flex;
  }
  .sideMenu {
    height: 100vh;
    width: 20%;
    padding: 0.2rem;
    background-color: #21212b;
  }
  .sideMenu li {
    margin: 0.5rem;
    display: flex;
    align-items: center;
  }
</style>
