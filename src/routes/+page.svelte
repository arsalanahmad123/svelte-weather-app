<script>
	import SearchArea from '../components/SearchArea.svelte';
</script>

<div
	class="container p-10 bg-slate-900 text-white h-screen mx-auto flex justify-center items-center"
>
	<div class="flex justify-center items-center flex-col">
		<h1 class="text-5xl break-words">Welcome to Our online Weather System</h1>
		<p class="text-lg mt-5">You can search for any country any location and get instant results</p>
		<button
			class="px-4 py-2 rounded-md bg-slate-600 font-bold mt-7 hover:shadow-lg shadow-slate-400"
			>Check Now
		</button>
	</div>
</div>
<section id="searchArea">
	<SearchArea />
</section>
