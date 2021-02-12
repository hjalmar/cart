<script>
  import Router, { context } from 'svelte-standalone-router';
  
  // components 
  import Index from '~/pages/Index.svelte';
  import Cart from '~/pages/Cart.svelte';
  import Masthead from '~/sections/masthead/Masthead.svelte';
  import Footer from '~/sections/footer/Footer.svelte';
  import Modal from '~/components/Modal.svelte';

  // routing for ease of expanding if time left
  const app = context({ initial: location.pathname });
  app.get('/', (req, res) => res.send(Cart));
</script>

<Masthead />
<main>
  <Router />
</main>
<Footer />
<Modal />

<style>
  main{
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    height: 100%;
  }
</style>