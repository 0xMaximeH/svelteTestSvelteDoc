<script>
  let count = 0
  const increment = () => {
    count += 1
  }
  
  $: doubled = count * 2;
  $: console.log('the count is ' + count);

  $: if (count >= 10) {
      alert('count is dangerously high!');
      count = 9;
    }


  let numbers = [1, 2, 3, 4];
  $: sum = numbers.reduce((t, n) => t + n, 0);
  function addNumber() {
    numbers.push(numbers.length + 1);
    numbers = numbers;
  }
    
</script>


<h3> Count clicks : </h3>
<button on:click={increment}>
  Clicked {count} {count === 1 ? 'time' : 'times'}
</button>

<p>{count} doubled is {count * 2} ou {doubled}</p>