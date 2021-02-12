<script>
  export const variant = '';
</script>

<button on:click class="{variant}">
  <slot>Button placeholder</slot>
</button>

<style>
  button{
    border: none;
    padding: 14rem 40rem;
    background-color: var(--color-beige);
    color: var(--color-dark);
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
</style>