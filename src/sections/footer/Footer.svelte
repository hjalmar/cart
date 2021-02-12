<script>
  import { location } from 'svelte-standalone-router';
  import Branding from '~/components/Branding.svelte';
  const links = [
    {slug: '/', label: 'accessoarer'},
    {slug: '/b', label: 'väskor'},
    {slug: '/c', label: 'skor'},
    {slug: '/d', label: 'varumärken'},
    {slug: '/e', label: 'outlet'}        
  ];

  const topbarLinks = [
    {slug: '/', label: 'kundservice'},
    {slug: '/', label: 'om oss'},
    {slug: '/', label: 'logga in'},     
  ];
</script>

<footer>
  <div class="max-width">
    <div class="branding">
      <Branding />
    </div>
    <nav>
      <ul>
        {#each links as {slug, label}}
          <li class:active={slug === $location}><a href="{slug}">{label}</a></li>
        {/each}
      </ul>

      <ul>
        {#each topbarLinks as {slug, label}}
          <li class:active={slug === $location}><a href="{slug}">{label}</a></li>
        {/each}
      </ul>
    </nav>
    <div class="social-media">
      <ul>
        <li><a href="/">instagram</a></li>
        <li><a href="/">facebook</a></li>
        <li><a href="/">twitter</a></li>
        <li><a href="/">youtube</a></li>
      </ul>
    </div>
    <p>
      Innehållet på denna webbplats är upphovsrättsskyddat och tillhör MODE FASHION. MODE FASHION affärskoncept går ut på att erbjuda mode och kvalitet till bästa pris.
    </p>
  </div>
</footer>
