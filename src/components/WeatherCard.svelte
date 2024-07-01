<script>
	export let data;
	export let cityName;
</script>

<section class="mt-10 flex justify-between items-center w-full">
	<h1 class="text-5xl font-bold text-white">{cityName}</h1>
	<div class="bg-white rounded-lg shadow-md p-6 mx-auto max-w-md">
		<div class="text-center">
			<h1 class="text-2xl font-semibold">Today's Weather</h1>
			<p class="text-gray-500">{data.current.condition.text}</p>
		</div>
		<div class="mt-4 flex justify-between items-center">
			<div>
				<p class="text-4xl font-semibold">
					{data.current.temp_c} <span class="font-bold"> C</span>
				</p>
				<p class="text-gray-500">{data.current.temp_f} <span class="font-bold">F</span></p>
			</div>
			<div>
				<img src={data.current.condition.icon} alt="Weather Icon" />
			</div>
		</div>
	</div>
</section>
