<script>
  import { location } from 'svelte-standalone-router';
  const links = [
    {slug: '/', label: 'accessoarer'},
    {slug: '/b', label: 'väskor'},
    {slug: '/c', label: 'skor'},
    {slug: '/d', label: 'varumärken'},
    {slug: '/e', label: 'outlet'}        
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
  }

  nav > ul > li{
    margin: 0 10rem;
  }

  nav > ul > li a{
    text-decoration: none;
  }

  li:hover{
    box-shadow: 0 3px 0 0 var(--color-gray);
  }

  .active, .active:hover{
    box-shadow: 0 3px 0 0 var(--color-teal);
  }
</style>