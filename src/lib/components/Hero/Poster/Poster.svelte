<script lang="ts">
	export let selectedMovie;
</script>

<div class="flex w-full flex-col items-start justify-start gap-4">
	<div class="flex w-full flex-col items-start justify-start gap-4">
		{#if selectedMovie}
			<img
				class=" max-w-72 self-center rounded-md md:self-start"
				src={`https://image.tmdb.org/t/p/w400${selectedMovie.poster_path}`}
				alt={selectedMovie.title}
			/>
		{/if}
	</div>
</div>
