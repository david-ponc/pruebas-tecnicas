<script lang="ts">
	import { readingListCount } from '../stores/library.store';
	import { cn } from '../utils';
	import { BookmarkSquareIcon } from './ui/icons';

	export let toggleReadingList: () => void;
	let isSticky = false;

	function scrollListener() {
		isSticky = window.scrollY > 0;
	}
</script>

<svelte:window on:scroll={scrollListener} />

<header
	class={cn(
		'z-10 flex items-center justify-between bg-slate-950 py-6 [transition:padding_128ms_ease]',
		isSticky && 'sticky top-0 py-4'
	)}
>
	<h1 class={cn('text-3xl font-bold [transition:font-size_128ms_ease]', isSticky && 'text-xl')}>
		Librería
	</h1>
	<button
		class={cn(
			'group/button flex items-center gap-2 rounded-md bg-slate-800 p-1.5 text-sm font-medium text-slate-300 shadow-sm',
			'transition-all duration-100 active:translate-y-px active:scale-x-[.98] active:scale-y-[.98] active:ring-0',
			'hover:text-sky-200 focus:text-sky-200',
			'md:px-3 md:py-1.5 md:pl-2.5'
		)}
		on:click={toggleReadingList}
	>
		<BookmarkSquareIcon
			class="transition-colors duration-150 group-hover/button:text-sky-300 group-focus/button:text-sky-300 md:text-slate-500"
		/>
		<span class="tabular-nums">{$readingListCount}</span>
		<span class="hidden md:inline">Lista de lectura</span>
	</button>
</header>
