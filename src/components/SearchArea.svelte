<script>
	const API_KEY = '60f43f93dc034e0897b114329233009';
	const BASE_URL = 'http://api.weatherapi.com/v1';
	import WeatherCard from './WeatherCard.svelte';

	let city = '';
	let weatherdata;

	async function getWeatherData() {
		if (city === '') {
			alert('Please enter a city');
		} else {
			const res = await fetch(`${BASE_URL}/current.json?key=${API_KEY}&q=${city}`);
			const data = await res.json();
			weatherdata = data;
			console.log(data);
		}
	}
</script>

<div class="bg-slate-950 p-5 flex justify-center items-center flex-col">
	<h2 class="text-3xl font-bold mb-10 text-center text-white">Search for any city</h2>
	<input
		type="text"
		name="city"
		bind:value={city}
		placeholder="Enter city name"
		class="w-full p-2 rounded border border-slate-400 outline-none focus:shadow shadow-slate-400 focus:outline focus:outline-1 focus:outline-slate-400 bg-slate-800 text-white focus:bg-slate-900 transition duration-300"
	/>
	<button
		class="mt-5 p-2 rounded-md bg-slate-300 font-bold hover:shadow-lg shadow-slate-400 w-full
		hover:bg-transparent
		hover:outline
		hover:outline-1
		hover:outline-slate-400 hover:text-white"
		on:click={getWeatherData}>Search</button
	>
	{#if weatherdata && city}
		<WeatherCard data={weatherdata} cityName={city} />
	{/if}
</div>
