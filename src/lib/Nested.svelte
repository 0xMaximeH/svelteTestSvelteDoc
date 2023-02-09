<script>

let string = `this string contains some <strong>HTML!!!</strong>`;


</script>

<p>This is a paragraph.</p>

<!-- Carefull with @html -->
<p>{@html string}</p>

<style>
	p {
		color: purple;
		font-family: 'Comic Sans MS', cursive;
	}
</style>
