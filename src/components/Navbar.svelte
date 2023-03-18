<script lang="ts">
  import Greeting from './Greeting.svelte';
  import { fly } from 'svelte/transition';
  import { page } from '$app/stores';
</script>

<header class="flex" data-justi-align="sb-center">
  <a class="logo-container block" href="/">
    <picture>
      <source height="32px" width="103.117px" srcset="/logo-aldi.svg" media="(min-width: 60rem)" />
      <img class="logo-image" src="/logo-aldi-small.svg" alt="Logo Aldwiputra" />
    </picture>
  </a>

  <div class="open-to-work-container" data-justi-align="sb-center" aria-hidden="true">
    <span class="green-light" />
    <p>open to work</p>
  </div>

  <nav>
    <ul class="flex">
      {#if $page.url.pathname === '/'}
        <li in:fly={{ y: -20, delay: 300 }}>
          <a href="/about">about</a>
        </li>
      {:else}
        <li in:fly={{ y: -20, delay: 300 }}>
          <a href="/">home</a>
        </li>
      {/if}
    </ul>
  </nav>

  <Greeting />
</header>

<style>
  header {
    padding-block: 2rem;
    z-index: 999;
    margin-block-end: 0.75rem;
    opacity: 0;
    animation-name: flyin-down, opacity;
    animation-duration: 500ms;
    animation-fill-mode: forwards;
    animation-timing-function: cubic-bezier(0.57, 0.21, 0.69, 1.25);
  }

  .logo-container {
    height: 1.75rem;
  }

  picture,
  img {
    height: 100%;
  }

  li {
    position: relative;
  }

  li::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    height: 1px;
    z-index: 1;
    width: 100%;
    background-color: rgba(var(--rgb-off-white));
  }

  .open-to-work-container {
    padding: 0.375rem 1.5rem;
    display: none;
    transform: translateX(-20%);
    border-radius: 1.5rem;
    border: 1px solid rgba(var(--rgb-off-white));
  }

  .open-to-work-container p {
    font-size: 0.75rem;
    font-weight: 300;
    margin-left: 1rem;
  }

  .green-light {
    display: block;
    width: 0.5rem;
    height: 0.5rem;
    background-color: rgba(22, 163, 74);
    border-radius: 50%;
    box-shadow: 0 0 0.6rem 0.1rem rgba(22, 163, 74, 0.7);
    transform: scale(0.75);
    animation-name: beating;
    animation-duration: 1500ms;
    animation-fill-mode: forwards;
    animation-iteration-count: infinite;
    animation-timing-function: ease-in;
  }

  nav {
    display: none;
  }

  nav ul {
    text-transform: capitalize;
    font-size: 0.875rem;
    font-weight: 400;
  }

  svg {
    width: 0.7em;
    transform: translateY(10%);
    margin-left: 0.2rem;
  }

  @keyframes beating {
    50% {
      transform: scale(1);
    }
    100% {
      transform: scale(0.75);
    }
  }

  @keyframes flyin-down {
    from {
      transform: translate3d(0, -100%, 0);
    }
    to {
      transform: translate3d(0, 0%, 0);
    }
  }

  @media screen and (min-width: 60rem) {
    .open-to-work-container {
      display: flex;
    }

    nav {
      display: block;
    }

    .logo-container {
      height: 2rem;
    }

    li {
      transform-origin: center;
      transition: transform linear 50ms;
      will-change: transform;
    }

    li:hover {
      transform: scale(0.9);
    }
  }
</style>
