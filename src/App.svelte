<script>
	let random;
	function setRandom(){
		random = Math.floor(Math.random() * (100-0));
	}
</script>

<main>
	<nav class="navbar">
		<div class="label hero">BoolTox</div>
	</nav>
	<div class="container">
		<div class="grid">
			<div class="tool">
				<div class="img"></div>
				<div class="title">Random Number Generator</div>
				<div class="text-md">Generate a random number by clicking a button</div>
				<div class="inner-box">
					<div class="title">{random!==undefined?random:"???"}</div>
					<div class="button" on:click={setRandom}>Generate</div>
				</div>
			</div>
			<div class="tool"></div>

			<div class="tool sm"></div>
			<div class="tool sm"></div>
		</div>
	</div>
</main>

<style>

</style>