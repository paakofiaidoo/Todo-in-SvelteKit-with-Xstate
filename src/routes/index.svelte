<script>
  import { v4 as uuidv4 } from "uuid";
  import Collections from "$lib/CollectionItem.svelte";

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
  
</script>

<div class="collections">
  {#each collections as collection}
    <Collections {...collection} />
  {/each}
</div>

<style>
  .collections {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
</style>
