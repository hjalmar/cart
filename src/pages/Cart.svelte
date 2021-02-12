<script>
  import Product from "~/sections/cart/Product.svelte";
  import Button from '~/components/Button.svelte';
  import { clear } from '~/components/Modal.svelte';
</script>

<section class="cart">
  <header>
    <h1>Your shopping cart</h1>
    <Button variant="teal" on:click={_ => clear()}>Close</Button>
  </header>
  <div class="content-wrapper">
    <div class="products">
      <header></header>
      {#each {length: 2} as product}
        <Product 
          quantity={1}
          brand="Brand" 
          product="Oversize Blazer"
          meta={{
            color: 'black',
            size: 36
          }}
        />
      {/each}
    </div>
    <p>Could not find any products.</p>
  </div>
</section>

<style>
  section{
    padding: 30rem;
    width: 100%;
    max-width: var(--max-width);
    height: 800px;
    background: var(--color-salmon);
  }

  section > header{
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin: 0 0 30rem 0;
  }

  section > header > h1{
    font-size: 45rem;
  }

  section > .content-wrapper{
    padding: 40rem;
    background-color: var(--color-light);
  }
</style>