<script>
  import '../app.css';
  import { theme } from '../stores/themeStore.js';
  import ThemeSwitcher from '../components/1-atoms/ThemeSwitcher.svelte';
  import { browser } from '$app/environment';
  
  let { children } = $props();

  $effect(() => {
    if (browser) {
      document.body.className = $theme;
    }
  });
</script>

<main>
  {@render children()}
</main>

<ThemeSwitcher />