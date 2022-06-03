<script>
	// {
	//   type: 'blog',
	//   content: '',
	//   frontmatter: {
	//     title: 'This is a test post using Github Issues as CMS',
	//     description: 'Test description'
	//   },
	//   title: 'This is a test post using Github Issues as CMS',
	//   description: 'Test description',
	//   tags: [],
	//   slug: 'this-is-a-test-post-using-github-issues-as-cms',
	//   date: '2022-05-22T09:18:13.000Z',
	//   ghMetadata: {
	//     issueUrl: 'https://github.com/LucianVoju/vojulucian.com/issues/1',
	//     commentsUrl: 'https://api.github.com/repos/LucianVoju/vojulucian.com/issues/1/comments',
	//     title: 'welcome',
	//     created_at: '2022-05-22T09:18:13Z',
	//     updated_at: '2022-05-31T07:18:12Z',
	//     reactions: {
	//       url: 'https://api.github.com/repos/LucianVoju/vojulucian.com/issues/1/reactions',
	//       total_count: 0,
	//       '+1': 0,
	//       '-1': 0,
	//       laugh: 0,
	//       hooray: 0,
	//       confused: 0,
	//       heart: 0,
	//       rocket: 0,
	//       eyes: 0
	//     }
	//   }
	// }

	export let item;
	let date = new Date(item?.date).toISOString().slice(0, 10);
</script>

<div class="mb-4 w-full">
	<div class="flex flex-col-reverse justify-between md:flex-row">
		<a
			sveltekit:prefetch
			class="w-full text-gray-900 hover:text-lime-600 dark:text-gray-100 dark:hover:text-lime-100"
			href={`/` + item.slug}
			><h4 class="mb-2 w-full flex-auto text-lg font-medium md:text-xl">
				<!-- <span class="rounded bg-blue-700 p-1 text-xs text-white">Essay</span> -->
				<span>{item.title}</span>
			</h4></a
		>
		<div
			class="inline-flex flex-1 flex-row-reverse items-center justify-end md:flex-row md:justify-start"
		>
			{#if (item.ghMetadata && item.ghMetadata.reactions.total_count) || item.data?.devToReactions}
				<span
					class=" mr-2 min-w-[3rem] text-right font-mono text-xs text-gray-700 text-opacity-70 dark:text-gray-300"
					>{(item?.ghMetadata?.reactions?.total_count || 0) + (item?.data?.devToReactions || 0)} ♥</span
				>
			{/if}
			<p class="w-28 text-left text-gray-500 md:text-right">{date}</p>
		</div>
	</div>
	<p class="overflow-hidden text-ellipsis break-all text-sm text-gray-600 dark:text-gray-400">
		{item.description}
	</p>
</div>
