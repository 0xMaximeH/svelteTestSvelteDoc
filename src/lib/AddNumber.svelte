<script>

  let numbers = [1, 2, 3, 4];

  $: sum = numbers.reduce((t, n) => t + n, 0);

  function addNumber() {
    numbers.push(numbers.length + 1);
    numbers = numbers;
  }
    
</script>

<h3> Add a number to a list : </h3>
<p>{numbers.join(' + ')} = {sum}</p>

<button on:click={addNumber}>
	Add a number
</button>