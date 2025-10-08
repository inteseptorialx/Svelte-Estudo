<script>
  import { theme } from '../../stores/themeStore.js';
  

  function toggleTheme() {
    theme.update(currentValue => {
      return currentValue === 'light' ? 'dark' : 'light';
    });
  }
</script>

<button on:click={toggleTheme}>
  {#if $theme === 'light'}
    Escuro
  {:else}
    Claro
  {/if}
</button>

<style>
  button {
    padding: 1rem;
    border-radius: 12px;
    border: none;
    cursor: pointer;
    font-weight: 500;
    background-color:  var( --texto-principal);
    color: var(--fundo-secundario);
  }
</style>