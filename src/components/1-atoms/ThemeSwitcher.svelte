<script>
  import { theme } from '../../stores/themeStore.js';
  import LuaIcon from '$lib/icons/LuaIcon.svelte';
  import SolIcon from '$lib/icons/SolIcon.svelte';

  function toggleTheme() {
    theme.update(currentValue => {
      return currentValue === 'light' ? 'dark' : 'light';
    });
  }
</script>

<button on:click={toggleTheme}>
  {#if $theme === 'light'}
    <LuaIcon/>
  {:else}
    <SolIcon/>
  {/if}
</button>

<style>
  button {
    padding: 0.5rem;
    border-radius: 12px;
    border: solid 3px;
    border-color: var(--borda-sutil);
    cursor: pointer;
    font-weight: 500;
    background-color:  var( --fundo-secundario);
    color: var(--texto-secundario);
  }
  button:hover {
    background-color: var(--fundo-hover);
  }

  :global(button svg) {
    width: 24px;
    height: 24px;
    color: var(--borda-sutil);
  }
</style>