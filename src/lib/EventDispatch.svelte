<script>
	import { createEventDispatcher } from 'svelte';

  const dispatch = createEventDispatcher();

  function sayHello() {
    dispatch('message', {
      text: 'Hello!'
    });
}
</script>

<h3>Event dispatch </h3>
<button on:click={sayHello}>
	Click to say hello
</button>