<script context="module">
  // load post before rendering components
  export const load = async ({fetch, page: {params}}) => {
    const {slug} = params
    const res = await fetch(`/pages/${slug}.json`)

    if(res.ok) {
      const {page} = await res.json()
      // make page available as props
      return {props: {page}}
    }
  }
</script>

<script>
  // make posts availble to html template
  export let page;
</script>


<svelte:head>
  <title>Sparkles Blog | {page.title}</title>
</svelte:head>

<h1 class="text-4xl font-semibold mb-5">{page.title}</h1>

<article class="prose">
  {@html page.content.html}
</article>

