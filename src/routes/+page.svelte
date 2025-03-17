<script lang="ts">
	import type { PageData } from './$types';
	export let data: PageData;
	$: ({ articles } = data);
</script>

<div class="flex min-h-screen w-full flex-col gap-8 bg-gray-100 p-8 text-black md:flex-row">
	<div
		class="flex flex-col rounded-lg border-4 border-black bg-white p-6 shadow-[6px_6px_0px_#000] md:w-2/3 lg:w-1/2"
	>
		<h2 class="mb-4 text-3xl font-bold uppercase">Articles</h2>
		<div class="space-y-6">
			{#each articles as article}
				<article class="rounded-lg border-4 border-black bg-gray-200 p-4 shadow-[4px_4px_0px_#000]">
					<header class="text-xl font-bold uppercase">{article.title}</header>
					<p class="mt-2 text-gray-800">{article.content}</p>
					<div class="mt-4 flex justify-between">
						<form action="?/deleteArticle&id={article.id}" method="POST">
							<button
								type="submit"
								class="rounded-lg border-4 border-black bg-red-400 px-4 py-2 font-bold uppercase shadow-[3px_3px_0px_#000] transition hover:bg-red-500"
								>Delete</button
							>
						</form>
						<a
							href="/{article.id}"
							role="button"
							class="rounded-lg border-4 border-black bg-blue-400 px-4 py-2 font-bold uppercase shadow-[3px_3px_0px_#000] transition hover:bg-blue-500"
							>Edit</a
						>
					</div>
				</article>
			{/each}
		</div>
	</div>

	<form
		action="?/createArticle"
		method="POST"
		class="max-w-md rounded-lg border-4 border-black bg-white p-6 shadow-[6px_6px_0px_#000] md:w-1/3 lg:w-1/2"
	>
		<h3 class="mb-4 text-3xl font-bold uppercase">New Article</h3>
		<label for="title" class="block font-bold">Title</label>
		<input
			type="text"
			id="title"
			name="title"
			class="mt-1 w-full rounded-lg border-4 border-black bg-gray-200 p-2 shadow-[3px_3px_0px_#000] focus:border-black focus:ring-black"
		/>

		<label for="content" class="mt-4 block font-bold">Content</label>
		<textarea
			id="content"
			name="content"
			rows="5"
			class="mt-1 w-full rounded-lg border-4 border-black bg-gray-200 p-2 shadow-[3px_3px_0px_#000] focus:border-black focus:ring-black"
		></textarea>

		<button
			type="submit"
			class="mt-4 w-full rounded-lg border-4 border-black bg-green-400 px-4 py-2 font-bold uppercase shadow-[3px_3px_0px_#000] transition hover:bg-green-500"
			>Add Article</button
		>
	</form>
</div>
