<script lang="ts">
	import { getGenreName } from '$lib/utils/genres';

	export let movie: any;
	export let showGenre: boolean = false;

	const genres = movie.genre_ids?.map((id: number) => getGenreName(id)).join(', ') || 'Unknown';
</script>

<div class="relative w-full cursor-pointer rounded-lg">
	<!-- Image Wrapper -->
	<div class="relative">
		<img
			class="w-full rounded-xl"
			src={`https://image.tmdb.org/t/p/w400${movie.poster_path}`}
			alt={movie.title}
		/>

		<div class="bg-accent absolute top-0 right-0 rounded-lg px-3 py-2 text-white">
			<p>⭐ {movie.vote_average.toFixed(1)}</p>
		</div>

		<div
			class="absolute inset-0 z-10 flex items-center justify-center rounded-lg bg-black/80 opacity-0 duration-300 hover:opacity-100"
		>
			<svg class="size-16" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512" fill="white">
				<path
					d="M464 256A208 208 0 1 0 48 256a208 208 0 1 0 416 0zM0 256a256 256 0 1 1 512 0A256 256 0 1 1 0 256zM188.3 147.1c7.6-4.2 16.8-4.1 24.3 .5l144 88c7.1 4.4 11.5 12.1 11.5 20.5s-4.4 16.1-11.5 20.5l-144 88c-7.4 4.5-16.7 4.7-24.3 .5s-12.3-12.2-12.3-20.9l0-176c0-8.7 4.7-16.7 12.3-20.9z"
				/>
			</svg>
		</div>
	</div>

	{#if showGenre}
		<div class="mt-3">
			<p class="font-semibold text-white lg:text-lg">{movie.title}</p>
			<p class="text-sm text-gray-400">{genres}</p>
		</div>
	{/if}
</div>
