<script>
  import Router, { context } from 'svelte-standalone-router';
  import Cart from './pages/Cart.svelte';

  // routing for ease of expanding if time left
  const app = context({ initial: location.pathname });
  app.get('/', (req, res) => res.send(Cart));
</script>


<main>
  <Router />
</main>

<style>
  main{
    display: flex;
    width: 100%;
    height: 100%;
  }
</style>