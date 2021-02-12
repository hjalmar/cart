<script>
  import Product from "~/sections/cart/Product.svelte";
  import Button from '~/components/Button.svelte';
  import { clear } from '~/components/Modal.svelte';
</script>

<section class="cart" role="dialog" aria-labelledby="label-heading">
  <header>
    <h1 id="label-heading">Your shopping cart</h1>
    <Button variant="teal" on:click={_ => clear()} aria-label="Close">Close</Button>
  </header>
  <div class="content-wrapper">
    <div class="cart-content">
      <header>
        <span>Product</span>
        <span>Quantity</span>
        <span>Price</span>
      </header>
      <div class="products">
        {#each {length: 4} as product}
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
    </div>
    
    <div class="checkout-information">      
      <div class="cart-summary">
        <div class="discount">
          <header>
            <h3>10% discount on your order</h3>
          </header>
          <p>As a first time shopper you get discount on your first order.</p>
        </div>
        <ul>
          <li><em class="danger-text">Discount -500 SEK</em></li>
          <li><span>Total 3,458 SEK</span></li>
        </ul>
      </div>
  
      <div class="actions">
        <Button on:click={_ => clear()} slim>
          <slot slot="icon">
            <svg xmlns="http://www.w3.org/2000/svg" width="192" height="192" fill="#000000" viewBox="0 0 256 256"><rect width="256" height="256" fill="none"></rect><polyline points="160 208 80 128 160 48" fill="none" stroke="#000000" stroke-linecap="round" stroke-linejoin="round" stroke-width="16"></polyline></svg>
          </slot>
          Continue shopping
        </Button>
  
        <Button variant="teal">
          <slot slot="icon">
            <svg xmlns="http://www.w3.org/2000/svg" width="192" height="192" fill="#000000" viewBox="0 0 256 256"><rect width="256" height="256" fill="none"></rect><rect x="24" y="56" width="208" height="144" rx="8" stroke-width="16" stroke="#000000" stroke-linecap="round" stroke-linejoin="round" fill="none"></rect><line x1="167.99414" y1="168" x2="199.99414" y2="168" fill="none" stroke="#000000" stroke-linecap="round" stroke-linejoin="round" stroke-width="16"></line><line x1="119.99414" y1="168" x2="135.99414" y2="168" fill="none" stroke="#000000" stroke-linecap="round" stroke-linejoin="round" stroke-width="16"></line><line x1="23.99414" y1="96.85228" x2="231.99412" y2="96.85228" fill="none" stroke="#000000" stroke-linecap="round" stroke-linejoin="round" stroke-width="16"></line></svg>
          </slot>
          Checkout
        </Button>
      </div>
    </div>

  </div>
</section>

<style>
  section{
    padding: 30rem;
    width: 100%;
    max-width: var(--max-width);
    height: 100%;
    max-height: calc(100vh - 60rem);
    background: var(--color-salmon);
    overflow-y: hidden;
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
    display: grid;
    grid-template-rows: auto auto;
    background-color: var(--color-light);
    height: calc(100% - 80rem);
  }

  .products{
    padding: 40rem 0;
  }

  .cart-content > header{
    display: grid;
    grid-template-columns: 2fr 1fr 1fr;
    position: sticky;
    top: 0;
    margin: 0;
    padding: 30rem 0 10rem;
    background-color: var(--color-light);
    border-bottom: 2px solid var(--color-gray);
  }

  .cart-content > header > span{
    color: var(--color-dark);
  }

  .cart-content > header > *{
    display: flex;
    justify-content: center;
  }
  .cart-content > header > *:first-child{
    justify-self: flex-start;
  }
  .cart-content > header > *:last-child{
    justify-self: flex-end;
  }

  .cart-content{
    padding: 0 40rem;
    height: 100%;
    overflow-y: scroll;
  }

  .cart-content :global(.product){
    display: grid;
    grid-template-columns: 2fr 1fr 1fr;
  }

  .cart-summary{
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 20rem 40rem;
    border-top: 2px solid var(--color-gray);
  }

  .discount{
    padding: 20rem;
    border: 2px solid var(--color-gray);
    width: 65%;
  }

  .cart-summary ul{
    list-style: none;
    text-align: right;
  }


  .actions{
    border-top: 2px solid var(--color-gray);
    display: flex;
    justify-content: space-between;
    padding: 40rem 50rem 40rem 35rem;
  }
  
</style>