<script>
  import { location } from 'svelte-standalone-router';
  const links = [
    {slug: '/', label: 'accessoarer'},
    {slug: '/', label: 'väskor'},
    {slug: '/', label: 'skor'},
    {slug: '/', label: 'varumärken'},
    {slug: '/', label: 'outlet'}        
  ];
</script>

<nav>
  <ul>
    {#each links as {slug, label}}
      <li class:active={slug === $location}><a href="{slug}">{label}</a></li>
    {/each}
  </ul>
</nav>

<style>
  nav > ul{
    display: flex;
    list-style: none;
    text-transform: uppercase;
    font-weight: bold;  
  }

  nav > ul > li{
    margin: 0 10rem;
  }

  nav > ul > li a{
    text-decoration: none;
  }
</style>