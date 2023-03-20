<script lang="ts">
  import { createEventDispatcher } from 'svelte';
  import All from './icons/All.svelte';
  import Mobile from './icons/Mobile.svelte';
  import Web from './icons/Web.svelte';

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
  style={text !== activeTab
    ? 'border: 1px solid var(--color-purple-subtext); color: var(--color-purple-subtext) ;'
    : 'border: 1px solid rgba(var(--rgb-off-white));color: rgba(var(--rgb-off-white));'}
>
  {#if text === 'all'}
    <All color={text === activeTab ? '#E2E8F0' : '#827796'} />
  {:else if text === 'mobile'}
    <Mobile color={text === activeTab ? '#E2E8F0' : '#827796'} />
  {:else}
    <Web color={text === activeTab ? '#E2E8F0' : '#827796'} />
  {/if}
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

  p {
    display: block;
    font-family: 'Atkinson Hyperlegible', sans-serif;
  }
</style>
