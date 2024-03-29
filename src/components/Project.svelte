<script lang="ts">
  import TechBox from './TechBox.svelte';

  export let title: string;
  export let imgPaths: string[] | string;
  export let techImgPaths: string[];
  export let url: string;

  function turnPathIntoAltText(path: string) {
    return path.replace('-', ' ').slice(0, -4);
  }
</script>

<a href={url} target="_blank" rel="noreferrer" class="project-container">
  <h3>{title}</h3>
  <div class="gallery-container flex">
    <div class="galleries shadow flex texturize">
      {#if typeof imgPaths === 'string'}
        <img src={imgPaths} alt={turnPathIntoAltText(imgPaths)} />
      {:else}
        <img src={imgPaths[0]} alt={turnPathIntoAltText(imgPaths[0])} />
        <img src={imgPaths[1]} alt={turnPathIntoAltText(imgPaths[1])} />
        <img src={imgPaths[2]} alt={turnPathIntoAltText(imgPaths[2])} />
      {/if}
    </div>
    <div class="tech-stack-container flex">
      <div class="img-container shadow texturize">
        <img src={techImgPaths[0]} alt="" />
      </div>
      <div class="img-container shadow texturize">
        <img src={techImgPaths[1]} alt="" />
      </div>
      <div class="img-container shadow texturize">
        <img src={techImgPaths[2]} alt="" />
      </div>
    </div>
  </div>
</a>

<style>
  .project-container {
    display: block;
    position: relative;
    padding-block: 2rem;
    border-bottom: 1px solid rgba(130, 119, 150, 0.1);
    cursor: pointer;
  }

  .project-container:hover {
    background-color: rgba(130, 119, 150, 0.1);
  }

  .project-container:first-child {
    border-top: 1px solid rgba(130, 119, 150, 0.1);
    margin-top: 1rem;
  }

  .project-container:hover h3 {
    background: linear-gradient(45deg, var(--color-blue-400) 0%, var(--color-purple-400) 75%);
    -webkit-text-fill-color: transparent;
    -moz-text-fill-color: transparent;
    -webkit-background-clip: text;
    background-clip: text;
    transform: translateX(2rem);
  }

  h3 {
    position: relative;
    color: var(--color-purple-subtext);
    z-index: 0;
    width: max-content;
    font-size: clamp(1rem, 4vw, 2rem);
    font-family: 'Atkinson Hyperlegible', sans-serif;
    font-weight: 400;
    white-space: nowrap;
    text-transform: uppercase;
    letter-spacing: 0.125rem;
    transition: all 200ms ease;
  }

  img {
    min-width: 0;
  }

  .gallery-container {
    margin-block-start: 1rem;
    margin-block-end: 1rem;
    gap: 1rem;
    align-items: flex-start;
  }

  .galleries {
    border-radius: 0.5rem;
    padding: 2rem;
    justify-content: center;
    align-items: center;
    background-color: var(--color-purple-600);
    overflow: hidden;
  }

  .tech-stack-container {
    flex-shrink: 0;
    flex-direction: column;
    gap: 1rem;
    /* width: clamp(3rem, 30vw, 12rem); */
    width: 13%;
    min-width: 2.5rem;
  }

  .img-container {
    border-radius: 0.5rem;
    padding: 0.75rem;
    background-color: var(--color-purple-600);
    overflow: hidden;
  }

  /* .img-container img {
		width: 100%;
	} */

  @media screen and (min-width: 45rem) {
    .img-container {
      padding: 1.25rem;
    }
  }

  @media screen and (min-width: 60rem) {
    .project-container:first-child {
      margin-top: 2.5rem;
    }

    .project-container:hover .gallery-container {
      opacity: 1;
      transform: scale(1) translateY(-30%);
    }

    .gallery-container {
      top: 0;
      right: 5%;
      z-index: 1000;
      position: absolute;
      pointer-events: none;
      width: clamp(30rem, 35vw, 35rem);
      opacity: 0;
      will-change: transform;
      transform: scale(0.5) translateY(-30%);
      transition: all 200ms cubic-bezier(0.23, 1, 0.32, 1);
      transform-origin: top right;
    }

    .gallery-container > * {
      flex-grow: 1;
    }

    .img-container {
      padding: 0.95rem;
    }
  }
</style>
