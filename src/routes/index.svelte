<script context="module">
  // load posts from /posts.json before rendering components
  export const load = async ({ fetch }) => {
    const res = await fetch('/posts.json');
    if (res.ok) {
      const { posts } = await res.json();
      // make posts available as props
      return { props: { posts } };
    }
  };
</script>

<script>
  // make posts availble to html template
  export let posts;
</script>

<svelte:head>
  <title>Blog | Welcome</title>
</svelte:head>

<h1 class="text-4xl mb010 font-extrabold">Blog</h1>

{#each posts as { title, slug, excerpt, coverImage, tags }}
  <div class="card text-center shadow-2xl mb-20">
    <figure class="px-10 pt-10">
      <img class="rounded-xl" src={coverImage.url} alt={`Cover image for ${title}`} />
    </figure>
    <div class="card-body">
      <h2 class="title">{title}</h2>
      <p>{excerpt}</p>

      <div class="flex justify-center mt-5 space-x-2">
        {#each tags as tag}
          <span class="badge badge-primary">{tag}</span>
        {/each}
      </div>

      <div class="justify-center card-actions">
        <a href="/posts/{slug}" class="btn btn-outline btn-primary">Read &rArr;</a>
      </div>
    </div>
  </div>
{/each}
