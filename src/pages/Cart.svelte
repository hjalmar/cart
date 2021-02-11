<script>
  import Product from "~/sections/cart/Product.svelte";
</script>

<section>
  <header>
    <h1>Your shopping cart</h1>
  </header>
  {#each {length: 2} as product}
    <div class="grid">
      <Product 
        quantity={1}
        brand="Brand" 
        product="Oversize Blazer"
        meta={{
          color: 'black',
          size: 36
        }}
      />
    </div>
  {:else}
    <p>Could not find any products.</p>
  {/each}
</section>

<style>
  section{
    padding: 30rem;
    width: 900px;
    height: 800px;
    background: crimson;
  }
</style>