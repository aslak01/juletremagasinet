<script> 
  import Posts from '../components/posts.svelte'
  
  let baseurl = 'https://7f4df120ff2e.ngrok.io'
  
  async function getRandomNumber() {
    const res = await fetch(`${baseurl}/wp-json/public-woo/v1/products/`);
    const text = await res.json();
    if (res.ok) {
      return text;
      // console.log(text)
    } else {
      throw new Error(text);
    }
  }

  let promise = getRandomNumber();

</script>

{#await promise then products}

<Posts {products} />

{/await}