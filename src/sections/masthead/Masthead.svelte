<script>
  import Topbar from './Topbar.svelte';
  import Branding from '~/components/Branding.svelte'; 
  import Navigate from './Navigation.svelte';
  import CartButton from './CartButton.svelte';
</script>

<header id="masthead">
  <Topbar />
  <div class="navigation max-width">
    <div class="branding">
      <Branding />
    </div>
    <Navigate />
    <CartButton />
  </div>
</header>


<style>
  #masthead{
    display: flex;
    flex-direction: column;
    justify-content: center;
    box-shadow: 0 1px 2px rgba(0, 0, 0, .12);
  }
  .branding{
    max-width: 120px;
  }
  .navigation{
    display: flex;
    align-self: center;
    width: 100%;
    align-items: center;
    justify-content: space-between;
    padding: 20rem 0;
  }
</style>