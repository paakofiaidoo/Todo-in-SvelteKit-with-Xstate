<script>
  //export let title, todos, id, icon;
  import { v4 as uuidv4 } from "uuid";
  let { title, todos, id, icon } = {
    id: uuidv4(),
    title: "School Todo List",
    icon: "https://img.icons8.com/material-outlined/50/ffffff/school.png",
    todos: [
      {
        title: "learn svelte",
        isComplete: false,
        id: uuidv4(),
      },
      {
        title: "leart svelte",
        isComplete: true,
        id: uuidv4(),
      },
    ],
  };
  let completed = todos.filter(({ isComplete }) => {
    return isComplete;
  });
  let uncompleted = todos.filter(({ isComplete }) => {
    return !isComplete;
  });
</script>

<content class="content">
  <div class="title">
    <img
      class="icon"
      src="https://img.icons8.com/material/48/000000/left--v1.png"
      alt="back"
    />
    <h2>{title}</h2>
  </div>
  <hr />

  <button class="addTask">
    <img
      class="icon"
      src="https://img.icons8.com/material-rounded/50/000000/add-property.png"
      alt="add"
    />
    <p>Add a task</p>
  </button>

  <hr />
  <div class="uncomplete">
    <h2 class="title">Task - {uncompleted.length}</h2>
    {#each uncompleted as { title, isComplete }}
      <div class="form-group">
        <input type="checkbox" id="first" checked={isComplete} />
        <label for="first">{title}</label>
      </div>
    {/each}
  </div>
  <div class="complete">
    <h2 class="title">Complete - {completed.length}</h2>
    {#each completed as { title, isComplete }}
      <div class="form-group">
        <input type="checkbox" id="first" checked={isComplete} />
        <label for="first">{title}</label>
      </div>
    {/each}
  </div></content
>
>

<style>
  .addTask {
    display: flex;
    flex-direction: row;
    background-color: transparent;
    border: none;
    align-items: center;
    justify-content: flex-start;
    color: #fff;
  }
  .content {
    justify-content: flex-start;
    align-items: center;
    width: 100%;
    display: flex;
    flex-direction: column;
  }
  .content div {
    width: 80%;
  }
  .content .title {
    align-items: center;
  }
  .content hr {
    width: 80%;
    opacity: 0.2;
  }
  .content .addTask {
    background-color: transparent;
    border: none;
    align-items: center;
    justify-content: flex-start;
    color: #fff;
  }
  .content .new {
    padding: 50px;
  }
  .content .form-group {
    display: flex;
    width: 80%;
    margin-bottom: 1rem;
    padding: 1rem;
    background: rgba(24, 24, 32, 0.15);
    box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.37);
    backdrop-filter: blur(16.5px);
    -webkit-backdrop-filter: blur(16.5px);
    border-radius: 10px;
    border: 1px solid rgba(255, 255, 255, 0.18);
  }
  .content .form-group input {
    padding: 0;
    height: initial;
    width: initial;
    margin-bottom: 0;
    display: none;
    cursor: pointer;
  }
  .content .form-group label {
    position: relative;
    cursor: pointer;
  }
  .content .form-group label:before {
    content: "";
    -webkit-appearance: none;
    background-color: transparent;
    border: 2px solid #0079bf;
    box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05),
      inset 0px -15px 10px -12px rgba(0, 0, 0, 0.05);
    padding: 10px;
    display: inline-block;
    position: relative;
    vertical-align: middle;
    cursor: pointer;
    margin-right: 5px;
    border-radius: 1rem;
  }
  .content .form-group input:checked + label:after {
    content: "";
    display: block;
    position: absolute;
    top: 2px;
    left: 9px;
    width: 6px;
    height: 14px;
    border: solid #0079bf;
    border-width: 0 2px 2px 0;
    transform: rotate(45deg);
  }
</style>
