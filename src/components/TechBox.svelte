<script lang="ts">
  export let path: string;

  $: altText = path.replace('-', ' ').slice(0, -4);
</script>

<div class="shadow">
  <img src={path} alt={altText} />
</div>

<style>
  div {
    background-color: var(--color-purple-600);
    display: grid;
    place-items: center;
    border-radius: 0.5rem;
    width: clamp(3rem, 14vw, 5.5rem);
    height: clamp(3rem, 14vw, 5.5rem);
    will-change: transform opacity;
    opacity: 0;
    animation-name: flyin;
    animation-duration: 600ms;
    animation-fill-mode: forwards;
    animation-timing-function: cubic-bezier(0.57, 0.21, 0.69, 1.25);
  }

  div:last-child {
    display: none;
  }

  img {
    height: clamp(1.75rem, 8vw, 3rem);
  }

  div:nth-child(1) {
    animation-delay: 200ms;
  }

  div:nth-child(2) {
    animation-delay: 250ms;
  }

  div:nth-child(3) {
    animation-delay: 300ms;
  }
  div:nth-child(4) {
    animation-delay: 350ms;
  }
  div:nth-child(5) {
    animation-delay: 400ms;
  }
  div:nth-child(6) {
    animation-delay: 450ms;
  }

  @media screen and (min-width: 60rem) {
    div:last-child {
      display: grid;
    }
  }
</style>
