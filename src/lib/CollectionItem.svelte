<script>
  export let title, icon, id;
</script>

<li class="menuItem">
  <a href={`/${id}`}>
    <img class="icon" alt={title} src={icon} />
    <h3>{title}</h3>
  </a>
</li>
<hr />

<style>
  hr {
    width: 80%;
    height: 2px;
    color: #666;
  }
  li a {
    margin: 0.5rem;
    display: flex;
    align-items: center;
  }
</style>
