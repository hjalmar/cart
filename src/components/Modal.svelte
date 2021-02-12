<script context="module">
  import { writable } from 'svelte/store';
  const modal = writable();
  export const push = (svelteComponent) => modal.set(svelteComponent);
  export const clear = _ => modal.set(undefined);
</script>

{#if $modal}
  {#key $modal}
    <div class="modal">
      hello
      <svelte:component this={$modal} />
    </div>
  {/key}
{/if}

<style>
  .modal{
    position: fixed;
    top: 0;
    left: 0;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: rgba(0, 0, 0, .8);
    width: 100vw;
    height: 100vh;
  }
</style>
