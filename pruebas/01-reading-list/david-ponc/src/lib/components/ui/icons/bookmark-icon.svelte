<script lang="ts">
	import { cn } from '~/lib/utils';
</script>

<svg
	{...$$props}
	fill="none"
	viewBox="0 0 24 24"
	stroke-width="1.5"
	stroke="currentColor"
	class={cn('h-6 w-6', $$props.class)}
>
	<path
		stroke-linecap="round"
		stroke-linejoin="round"
		d="M17.593 3.322c1.1.128 1.907 1.077 1.907 2.185V21L12 17.25 4.5 21V5.507c0-1.108.806-2.057 1.907-2.185a48.507 48.507 0 0111.186 0z"
	/>
</svg>
