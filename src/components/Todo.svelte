<script>
  import { deleteTodo, toggleTodoCompleted } from "../stores/todoStore";
  export let todo;
</script>

<li
  class="flex items-center shadow-sm border border-gray-200 rounded-lg my-2 py-2 px-4"
>
  <input
    name="completed"
    type="checkbox"
    checked={todo.completed}
    on:change={() => toggleTodoCompleted(todo.id)}
    class="mr-2 form-checkbox h-5 w-5"
  />
  <span class={`flex-1 text-gray-800 ${todo.completed ? "line-through" : ""}`}
    >{todo.text}</span
  >
  <button
    type="button"
    class="middle none center mr-3 rounded-lg bg-pink-500 py-2 px-4 font-sans text-xs font-bold uppercase text-white shadow-md shadow-pink-500/20 transition-all hover:shadow-sm hover:shadow-pink-500/40 focus:opacity-[0.85] focus:shadow-none active:opacity-[0.85] active:shadow-none disabled:pointer-events-none disabled:opacity-50 disabled:shadow-none"
    data-ripple-light="true"
    on:click={() => deleteTodo(todo.id)}
  >
    Delete
  </button>
</li>
