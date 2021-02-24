<script> 
  import Post from './post.svelte'
  export let products
</script>

{#each products as product}
  <Post {product} />
{/each}
