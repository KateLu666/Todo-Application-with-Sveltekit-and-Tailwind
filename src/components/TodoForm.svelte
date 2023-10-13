<script>
  import { addTodo } from "../stores/todoStore.js";
  let todo = "";
  const handleSubmit = () => {
    addTodo(todo);
    todo = "";
    console.log("submitting");
  };
</script>

<form class="my-6" on:submit|preventDefault={handleSubmit}>
  <div class="flex flex-col text-sm mb-2">
    <label class="font-bold mb-2 text-gray-800" for="todo">Todo</label>
    <input
      type="text"
      bind:value={todo}
      id="todo"
      name="todo"
      placeholder="Add a todo"
      class="appearance-none shadown-sm border border-gray-200 p-2 focus:outline-none focus:border-gray-500 rounded-lg"
    />
  </div>
  <button
    type="submit"
    class="w-full rounded-lg bg-teal-500 py-3 px-6 my-4 font-sans text-xs font-bold uppercase text-white shadow-md shadow-teal-500/20 transition-all hover:shadow-lg hover:shadow-teal-500/40 focus:opacity-[0.85] focus:shadow-none active:opacity-[0.85] active:shadow-none disabled:pointer-events-none disabled:opacity-50 disabled:shadow-none"
    data-ripple-light="true"
  >
    submit
  </button>
</form>
