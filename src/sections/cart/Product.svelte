<script>
  import Button from "~/components/Button.svelte";
  import Quantity from "~/sections/cart/Quantity.svelte";

  export let quantity = 1;
  export let brand;
  export let product;
  export let meta;
</script>

<div class="product">
  <div class="product-info">
    <div class="image">
      <img src="" alt="">
    </div>

    <div class="content">
      <header>
        <h3>{brand}</h3>
        <h4>{product}</h4>
      </header>
      <p class="meta">
        <span class="color" style="--color: {meta.color}">{meta.color}</span>
        <span>{meta.color}</span>, <span>size {meta.size}</span>
      </p>

      <div class="actions">
        <Button variant="teal" aria-label="Change">Change</Button>
        <Button variant="danger" aria-label="Remove">Remove</Button>
      </div>
    </div>
  </div>

  <div class="quantity">
    <Quantity value={quantity} min={10} />
  </div>

  <div class="price">
    <span class="price-amount">1832</span><span class="price-currency">sek</span>
  </div>

</div>

<style>
  .product{
    display: grid;
    grid-template-columns: repeat(3, auto);
    width: 100%;
    gap: 10rem;
    align-items: center;
  }
  .product::after{
    content: '';
    height: 2px;
    width: 100%;
    margin: 25rem 0 35rem;
    grid-column: 1 / 4;
    background-color: var(--color-gray);
  }
  .product > *{
    display: flex;
    justify-content: center;
  }
  .product > *:first-child{
    justify-self: flex-start;
  }
  .product > *:last-child{
    justify-self: flex-end;
  }

  .product-info{
    display: grid;
    gap: 20rem;
    grid-template-columns: repeat(2, auto);
  }

  .image{
    width: 200px;
    height: 220px;
    background: var(--color-gray);
  }

  .product-info .content{
    padding: 20rem 0;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }

  .meta{
    display: flex;
    align-items: center;
  }
  .meta > span::first-letter{
    text-transform: capitalize;
  }
  .meta .color{
    overflow: hidden;
    margin-right: 10rem;
    width: 30rem;
    height: 30rem;
    text-indent: -99999px;
    background-color: var(--color);
  }

  .actions{
    display: grid;
    grid-template-columns: repeat(2, auto);
    gap: 10rem;
  }

</style>