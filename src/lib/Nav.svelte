<script>
  export let path;

  console.log(path, path !== "/");
  if (path !== "/") {
    path = path.split("/")[1];
    path = path[0].toUpperCase() + path.slice(1);
  }
</script>

<nav>
  {#if path === "/"}
    <h3>Collections</h3>
  {:else}<h3><a href="/">Collections </a>: {path}</h3>
  {/if}
</nav>

<style>
  nav {
    display: flex;
    list-style: none;
    background-color: #21212b;
    color: #bbb;
    padding: 0.5rem;
  }
  li {
    margin: auto;
  }
  a {
    color: inherit;
    text-decoration: none;
    text-transform: capitalize;
  }
</style>
