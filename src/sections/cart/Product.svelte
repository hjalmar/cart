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
      <h3>{brand}</h3>
      <h4>{product}</h4>
      <p class="meta">
        <span class="color" style="--color: {meta.color}">{meta.color}</span>
        <span>{meta.color}</span>, <span>{meta.size}</span>
      </p>

      <div class="actions">
        <Button>Change</Button>
        <Button>Delete</Button>
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
</style>