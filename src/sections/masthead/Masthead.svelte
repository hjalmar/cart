<script>
  import Topbar from './Topbar.svelte';
  import Branding from '~/components/Branding.svelte'; 
  import Navigate from './Navigation.svelte';
</script>

<header id="masthead">
  <Topbar />
  <div>
    <Branding />
    <Navigate />
    <!-- <Cart /> -->
  </div>
</header>
