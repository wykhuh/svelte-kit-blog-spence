<script context="module">
  export const load = async ({ fetch }) => {
    const res = await fetch('/pages.json')
    if (res.ok) {
      const { pages } = await res.json()
      return {
        props: { pages },
      }
    }
  }
</script>

<script>
  import Nav from '../components/nav.svelte'
  export let pages;
  import '../app.css';
</script>

<Nav {pages}/>

<main class="container max-w-xl mx-auto px-4">
  <slot />
</main>

