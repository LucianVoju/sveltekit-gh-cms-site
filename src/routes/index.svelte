<script context="module">
	import {
		SITE_URL,
		REPO_URL,
		SITE_TITLE,
		SITE_DESCRIPTION,
		DEFAULT_OG_IMAGE,
		MY_TWITTER_HANDLE
	} from '$lib/siteConfig';
	export const prerender = true;
</script>

<script>
	import Newsletter from '../components/Newsletter.svelte';
	import FeatureCard from '../components/FeatureCard.svelte';
</script>

<svelte:head>
	<title>{SITE_TITLE}</title>
	<link rel="canonical" href={SITE_URL} />
	<link rel="alternate" type="application/rss+xml" href={SITE_URL + '/api/rss.xml'} />
	<meta property="og:url" content={SITE_URL} />
	<meta property="og:type" content="article" />
	<meta property="og:title" content={SITE_TITLE} />
	<meta name="Description" content={SITE_DESCRIPTION} />
	<meta property="og:description" content={SITE_DESCRIPTION} />
	<meta property="og:image" content={DEFAULT_OG_IMAGE} />
	<meta name="twitter:card" content="summary" />
	<meta name="twitter:creator" content={'@' + MY_TWITTER_HANDLE} />
	<meta name="twitter:title" content={SITE_TITLE} />
	<meta name="twitter:description" content={SITE_DESCRIPTION} />
	<meta name="twitter:image" content={DEFAULT_OG_IMAGE} />
</svelte:head>

<div
	class="mx-auto flex w-full max-w-4xl flex-col items-start justify-center border-gray-200 px-4 pb-16 dark:border-gray-700 sm:px-8"
>
	<div class="flex flex-col-reverse items-start sm:flex-row">
		<div class="mb-16 flex flex-col pr-8 ">
			<h1 class="mb-3 text-3xl font-bold tracking-tight text-black dark:text-white md:text-5xl">
				Voju
				<span
					class="relative ml-2 inline-block before:absolute before:-inset-1 before:block before:-skew-y-3 before:bg-teal-700"
				>
					<span class="relative skew-y-3 text-white">{SITE_TITLE}</span>
				</span>
				.com
			</h1>
			<h2 class="mb-4 text-gray-700 dark:text-gray-200">
				Full Stack JavaScript Developer, Weightlifter, Continuous Learner. Now I build things at
				<a
					class=" inline-block"
					target="_blank"
					rel="noopener noreferrer"
					href="https://www.linkedin.com/company/nagarro">Nagarro</a
				>
			</h2>

			<a class="text-gray-600 dark:text-gray-400" href="/about">More on About page</a>
		</div>
		<img
			alt="Lucian Voju"
			src="/my_image.webp"
			class="relative mb-8 mr-auto w-[80px] rounded-full bg-cyan-300 bg-opacity-25 sm:mb-0 sm:w-[176px]"
		/>
	</div>

	<section class="mb-16 w-full">
		<h3 class="mb-6 text-2xl font-bold tracking-tight text-black dark:text-white md:text-4xl">
			Featured Posts
		</h3>
		<div class="flex flex-col gap-6 md:flex-row">
			<FeatureCard
				title="This is a test post using Github Issues as CMS"
				href="/this-is-a-test-post-using-github-issues-as-cms"
				stringData="June 2022"
			/>
		</div>
		<a
			class="mt-8 flex h-6 rounded-lg leading-7 text-gray-600 transition-all dark:text-gray-400 dark:hover:text-gray-200"
			href="/blog"
			>See latest posts<svg
				xmlns="http://www.w3.org/2000/svg"
				fill="none"
				viewBox="0 0 24 24"
				class="ml-1 h-6 w-6"
				><path
					stroke="currentColor"
					stroke-linecap="round"
					stroke-linejoin="round"
					stroke-width="2"
					d="M17.5 12h-15m11.667-4l3.333 4-3.333-4zm3.333 4l-3.333 4 3.333-4z"
				/></svg
			></a
		>
	</section>
	<!-- <Newsletter /> -->
</div>
