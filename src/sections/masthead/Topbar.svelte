<script>
  import { location } from 'svelte-standalone-router';
  import Search from './Search.svelte';
  const links = [
    {slug: '/', label: 'kundservice'},
    {slug: '/', label: 'om oss'},
    {slug: '/', label: 'logga in'},     
  ];
</script>

<section id="top-bar">
  <div class="max-width">
    <Search placeholder="Sök" />
    <ul>
      {#each links as {slug, label}}
        <li class:active={slug === $location}><a href="{slug}">{label}</a></li>
      {/each}
    </ul>
  </div>
</section>


<style>
  .max-width{
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
  }
  section{
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 4rem 0;
    background-color: var(--color-salmon);
  }
  ul{
    display: flex;
    font-size: 14rem;
    list-style: none;
    text-transform: uppercase;
  }
  ul > li{
    margin: 0 10rem;
  }
  ul > li:last-child{
    margin: 0;
  }
  a{
    text-decoration: none;
  }
</style>