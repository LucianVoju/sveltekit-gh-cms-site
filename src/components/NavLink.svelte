<script>
	import { page } from '$app/stores';
	$: isActive = $page.url.pathname === $$props.href;

	/**
	 * @type {string}
	 */
	export let href;
</script>

<a
	class="hidden rounded-lg p-1 text-gray-800 transition-all hover:bg-lime-200 dark:text-gray-200 dark:hover:bg-lime-800 sm:px-3 sm:py-2 md:inline-block"
	class:font-semibold={isActive}
	{href}
	><span class="capsize"><slot /> </span>
</a>
