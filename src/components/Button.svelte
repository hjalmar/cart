<script>
  export let variant = '';
</script>

<button on:click class="{variant}" {...$$restProps}>
  <slot name="icon" />
  <div class="content">
    <slot>Button placeholder</slot>
  </div>
</button>

<style>
  button{
    display: flex;
    align-items: center;
    border: none;
    padding: 14rem 40rem;
    background-color: transparent;
    color: var(--color-dark);
  }
  button :global(svg){
    max-width: 30px;
    height: auto;
    width: 100%;
  }
  .content:first-child:not(:last-child){
    margin-right: 15rem;
  }
  .content:last-child:not(:first-child){
    margin-left: 15rem;
  }
  .beige{
    background-color: var(--color-beige);
    color: var(--color-light);
  }
  .salmon{
    background-color: var(--color-salmon);
  }
  .teal{
    background-color: var(--color-teal);
  }
  .danger{
    background-color: var(--color-red);
  }
</style>