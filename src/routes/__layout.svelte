<script context="module">
	import { MY_TWITTER_HANDLE, SITE_TITLE, GH_USER } from '$lib/siteConfig';
</script>

<script>
	import '../tailwind.css';
	import Nav from '../components/Nav.svelte';
</script>

<svelte:head>
	<link href="https://github.com/LucianVoju" rel="me" />
	<link
		rel="alternate"
		type="application/rss+xml"
		title={'RSS Feed for ' + SITE_TITLE}
		href="/rss.xml"
	/>
</svelte:head>

<div class="flex flex-col justify-center bg-gray-50 px-4 dark:bg-slate-900 sm:px-8">
	<Nav />
</div>
<main class=" flex flex-1 flex-col  bg-gray-50 px-4 dark:bg-gray-900 sm:px-8">
	<slot />
</main>

<footer class="mx-auto mb-8 flex w-full max-w-4xl flex-col items-start justify-center">
	<hr class="border-1 mb-8 w-full border-gray-200 dark:border-slate-800" />
	<div class="grid w-full max-w-4xl grid-cols-1 gap-4 px-4 pb-16 sm:grid-cols-2 sm:px-8">
		<div class="flex flex-col space-y-4">
			<a class="text-gray-500 transition hover:text-gray-300" href="/">Home</a>
			<a class="text-gray-500 transition hover:text-gray-300" href="/about">About</a>
			<!-- <a class="text-gray-500 transition hover:text-gray-300" href="/#newsletter">Newsletter</a> -->
		</div>
		<div class="flex flex-col space-y-4">
			<a
				class="text-gray-500 transition hover:text-gray-300"
				target="_blank"
				rel="noopener noreferrer"
				href={'https://twitter.com/intent/follow?screen_name=' + MY_TWITTER_HANDLE}
			>
				Twitter
			</a>
			<a
				class="text-gray-500 transition hover:text-gray-300"
				target="_blank"
				rel="noopener noreferrer"
				href={GH_USER}
			>
				GitHub
			</a>
		</div>
	</div>
	<p class="prose px-4 dark:prose-invert sm:px-8">
		This website is based on the
		<a target="_blank" rel="noopener noreferrer" href="https://swyxkit.netlify.app/">swyxkit</a>
		template.
	</p>
</footer>
