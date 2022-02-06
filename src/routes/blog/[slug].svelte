<script context="module">
	import { gql, GraphQLClient } from 'graphql-request';

	export const formatDate = (dateString) => {
		const options = { year: 'numeric', month: 'long', day: 'numeric' };
		return new Date(dateString).toLocaleDateString(undefined, options);
	};

	export async function load(context) {
		const graphcms = new GraphQLClient(import.meta.env.VITE_GRAPHCMS_URL, {
			headers: {}
		});

		const query = gql`
			query PostPageQuery($slug: String!) {
				post(where: { slug: $slug }) {
					title
					date
					content {
						html
					}
					tags
					author {
						id
						name
					}
				}
			}
		`;

		const variables = {
			slug: context.params.slug
		};

		const { post } = await graphcms.request(query, variables);

		return {
			props: {
				post
			}
		};
	}
</script>

<script>
	export let post;
</script>

<svelte:head>
	<title>{post.title}</title>
</svelte:head>

<h1 class="font-bold text-3xl tracking-tight text-center">{post.title}</h1>
<p class="text-gray-400 text-center my-2">{formatDate(post.date)} · {post.tags}</p>
<p>{post.author.name}</p>
{@html post.content.html}
