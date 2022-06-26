<script>
	import {fade} from 'svelte/transition';
	import { afterUpdate } from 'svelte';

	let random;
	let coin;
	let dice;
	let height;
	let weight;
	let bmi;
	let upper;
	let lower;

	function setRandom(){
		if(parseInt(lower)!==NaN && parseInt(upper)!==NaN){
			random = Math.floor(Math.random() * (parseInt(upper)-parseInt(lower)+1) + lower);
		}
	}

	function calcBMI(){
		bmi = (parseInt(weight)/(parseInt(height)*2/100)).toFixed(4);
	}

	function toss(){
		if(Math.round(Math.random())==1){
			coin = "Heads"
		}
		else{
			coin = "Tails"
		}
	}
	function roll(){
		dice = Math.floor(Math.random()*7);
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
				<div id="randomizer" class="inner-box">
					<div class="title" id="random">{random!==undefined?random:"???"}</div>
					<button class="button" on:click={setRandom}>Generate</button>
					<div class="text-md">Set a range</div>
					<div class="row">
						<input class="input" type="number" bind:value={lower} placeholder="From"/>
						<input class="input" type="number" bind:value={upper} placeholder="To"/>
					</div>
				</div>
			</div>
			<div id="bmicalc" class="tool">
				<div class="img"></div>
				<div class="title">BMI Calculator</div>
				<div class="text-md">Calculate your Body Mass Index</div>
				<div class="inner-box">
					<div class="row">
						<div class="label">Weight (kg)</div>
						<input class="input" type="number" bind:value={weight}/>
					</div>
					<div class="row">
						<div class="label">Height (cm)</div>
						<input class="input" type="number" bind:value={height}/>
					</div>
					<div class="title" id="bmi">Your BMI : {bmi!==undefined?bmi:"???"}</div>
					<button class="button" on:click={calcBMI}>Calculate</button>
				</div>
			</div>

			<div class="tool sm">
				<div class="img"></div>
				<div class="title">Toss a coin</div>
				<div class="title" id="coin">{coin!==undefined?coin:"???"}</div>
				<button class="button" on:click={toss}>Toss</button>
			</div>
			<div class="tool sm">
				<div class="img"></div>
				<div class="title">Roll a die</div>
				<div class="title" id="dice">{dice!==undefined?dice:"???"}</div>
				<button class="button" on:click={roll}>Roll</button>
			</div>
		</div>
	</div>
</main>

<style>

</style>