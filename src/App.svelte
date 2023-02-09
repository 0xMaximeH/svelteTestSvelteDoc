<script>

  import Counter from './lib/Counter.svelte'
  import AddNumber from './lib/AddNumber.svelte'
  import Nested from './lib/Nested.svelte';
  import ExportVariable from './lib/ExportVariable.svelte';
  import Info from './lib/Info.svelte';
  import LoggedIn from './lib/LoggedIn.svelte';
  import ForEach from './lib/ForEach.svelte';
  import ForEachObject from './lib/ForEachObject.svelte';
  import Await from './lib/Await.svelte';
  import MouseEvent from './lib/MouseEvent.svelte';
  import EventDispatch from './lib/EventDispatch.svelte';
  import CustomButton from './lib/CustomButton.svelte';
  import BindValue from './lib/BindValue.svelte';
  import ToDoDone from './lib/ToDoDone.svelte';
  import BindCss from './lib/BindCSS.svelte';
  import BindThis from './lib/BindThis.svelte';
  import BindComponent from './lib/BindComponent.svelte';
  import BindCompIns from './lib/BindCompIns.svelte';

	const pkg = {
		name: 'svelte',
		version: 3,
		speed: 'blazing',
		website: 'https://svelte.dev'
	};

  let alt = 'an image';
  let src = 'https://svelte.dev/tutorial/image.gif';
  let field;

  let things = [
		{ id: 1, name: 'apple' },
		{ id: 2, name: 'banana' },
		{ id: 3, name: 'carrot' },
		{ id: 4, name: 'doughnut' },
		{ id: 5, name: 'egg' },
	];

  let pin;
	$: view = pin ? pin.replace(/\d(?!$)/g, '•') : 'enter your pin';

	function handleSubmit3() {
		alert(`submitted ${pin}`);
	}

	function handleClick() {
		things = things.slice(1);
	}
  
  function handleMessage(event) {
		alert(event.detail.text);
	}

  function handleClick2() {
		alert("Button Clicked");
	}
</script>

<main>

  <h2> Hello {'maxime'.toUpperCase()}</h2>
  <img src={src} {alt}>

  <div class="card">
    <Counter />

    <Nested />

    <AddNumber />

    <ExportVariable answer='42'/>

    <Info {...pkg}/>

    <LoggedIn />

    <ForEach />

    <h3>
      For each object :
    </h3>

    <button on:click={handleClick}>
      Remove first thing
    </button>
    
    {#each things as thing (thing.id) }
      <ForEachObject name={thing.name}/>
    {/each}

    <Await />

    <MouseEvent />

    <EventDispatch on:message={handleMessage}/>

    <CustomButton on:click={handleClick2}/>

    <BindValue />

    <ToDoDone />

    <BindCss />

    <BindThis />
    <h3> Enter the pin</h3>
    <h3 style="color: {pin ? '#333' : '#ccc'}">{view}</h3>
    <BindComponent bind:value={pin} on:submit={handleSubmit3}/>

    <h3> Bind component instance</h3>
    <BindCompIns bind:this={field}/>
    <button on:click={() => field.focus()}>Focus field</button>
  </div>


  

  <p>
    Check out <a href="https://github.com/sveltejs/kit#readme" target="_blank" rel="noreferrer">SvelteKit</a>, the official Svelte app framework powered by Vite!
  </p>

</main>
