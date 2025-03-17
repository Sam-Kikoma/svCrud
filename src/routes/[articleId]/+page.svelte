<script lang="ts">
	import type { PageData } from './$types';
	export let data: PageData;
	$: ({ article } = data);
</script>

<form
	action="?/updateArticle"
	method="POST"
	class="max-w-md rounded-lg border-4 border-black bg-white p-6 shadow-[6px_6px_0px_#000] md:w-1/3 lg:w-1/2"
>
	<h3 class="mb-4 text-3xl font-bold uppercase">Editing {article.title}</h3>
	<label for="title" class="block font-bold">Title</label>
	<input
		value={article.title}
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
		value={article.content}
	></textarea>

	<button
		type="submit"
		class="mt-4 w-full rounded-lg border-4 border-black bg-green-400 px-4 py-2 font-bold uppercase shadow-[3px_3px_0px_#000] transition hover:bg-green-500"
		>Update Article</button
	>
</form>
