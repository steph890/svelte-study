<script>
	export let name = "world";
	console.log(name);
	$:console.log(name);
</script>

<input type=text bind:value={name}>

{@debug name}

<h1>Hello {name}! </h1>