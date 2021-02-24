<!-- App.svelte -->
<script> 
  import './main.css';
  import { Router } from '@roxi/routify';
  import { routes } from "./.routify/routes";
    
</script>
<!-- <button on:click={handleClick}>Get data</button> -->
<Router {routes} />
