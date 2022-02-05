<script context="module">
	import { gql, GraphQLClient } from 'graphql-request';

	export async function load() {
		const graphcms = new GraphQLClient(import.meta.env.VITE_GRAPHCMS_URL, {
			headers: {}
		});

		const query = gql`
			query PostsIndex {
				posts {
					id
					title
					slug
					date
					excerpt
				}
			}
		`;

		const { posts } = await graphcms.request(query);

		return {
			props: {
				posts
			}
		};
	}
</script>

<script>
	export let posts;
</script>

<h1 class="font-bold text-2xl">GraphCMS starter blog</h1>
<ul>
	{#each posts as post}
		<li>
			<a href="/blog/{post.slug}">{post.title}</a>
		</li>
	{/each}
</ul>
