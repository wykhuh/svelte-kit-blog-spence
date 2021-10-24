<script context="module">
  // load posts from /posts.json before rendering components
  export const load = async ({fetch}) => {
    const res = await fetch('/posts.json')
    if(res.ok) {
      const {posts} = await res.json()
      // make posts available as props
      return {props: {posts}}
    }
  }
</script>

<script>
  export let posts;
</script>

<pre>{JSON.stringify(posts, null, 2)}</pre>
