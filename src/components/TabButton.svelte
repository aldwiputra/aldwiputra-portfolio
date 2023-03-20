<script lang="ts">
  import { createEventDispatcher } from 'svelte';

  type Tab = 'all' | 'web' | 'mobile';

  export let path: string;
  export let text: Tab;
  export let activeTab: Tab;
  $: altText = path.replace('-', ' ').slice(0, -4);

  const dispatch = createEventDispatcher();

  function setActiveTab() {
    dispatch('change', { state: text });
  }
</script>

<button
  on:click={setActiveTab}
  class="flex"
  data-justi-align="sb-center"
  style={text.toLowerCase() !== activeTab
    ? 'border: 1px solid var(--color-purple-subtext); color: var(--color-purple-subtext) ;'
    : 'border: 1px solid rgba(var(--rgb-off-white));color: rgba(var(--rgb-off-white));'}
>
  <img src={path} alt={altText} />
  <p>
    {text[0].toUpperCase() + text.slice(1)}
  </p>
</button>

<style>
  button {
    background-color: transparent;
    cursor: pointer;
    font-size: 1rem;
    border-radius: 1rem;
    border: 1px solid rgba(var(--rgb-off-white));
    padding: 0.25rem 1rem;
  }

  img {
    height: 1em;
    margin-inline-end: 0.5rem;
  }

  p {
    display: block;
    font-family: 'Atkinson Hyperlegible', sans-serif;
  }
</style>
