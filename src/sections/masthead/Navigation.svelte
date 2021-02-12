<script>
  import { location } from 'svelte-standalone-router';
  const links = [
    {slug: '/', label: 'ACCESSOARER'},
    {slug: '/', label: 'VÄSKOR'},
    {slug: '/', label: 'SKOR'},
    {slug: '/', label: 'VARUMÄRKEN'},
    {slug: '/', label: 'OUTLET'}        
  ];
</script>

<nav>
  <ul>
    {#each links as {slug, label}}
      <li class:active={slug === $location}><a href="{slug}">{label}</a></li>
    {/each}
  </ul>
</nav>