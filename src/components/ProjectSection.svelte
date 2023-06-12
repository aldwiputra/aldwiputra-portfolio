<script lang="ts">
  import Project from './Project.svelte';
  import TabButton from './TabButton.svelte';

  type Project = {
    title: string;
    imgPaths: string[] | string;
    techImgPaths: string[];
    url: string;
    type: 'mobile' | 'web';
  };

  type Tab = 'all' | 'web' | 'mobile';

  let activeTab: Tab = 'all';

  const projectsData: Project[] = [
    {
      title: 'Racepeers',
      imgPaths: '/racepeers-banner.png',
      techImgPaths: ['/react-icon.svg', '/css.svg', '/typescript.svg'],
      url: 'https://racepeers.vercel.app',
      type: 'web'
    },
    {
      title: 'POTA Brand',
      imgPaths: '/pota-hero.png',
      techImgPaths: ['/html.svg', '/css.svg', '/javascript.svg'],
      url: 'https://potabrand.aldwiputra.site',
      type: 'web'
    },
    {
      title: 'Cliqengo',
      imgPaths: '/cliqengo-homepage.png',
      techImgPaths: ['/html.svg', '/css.svg', '/javascript.svg'],
      url: 'https://cliqengo.aldwiputra.site',
      type: 'web'
    },
    {
      title: 'Bingify',
      imgPaths: '/bingify-hero.png',
      techImgPaths: ['/svelte.svg', '/css.svg', '/typescript.svg'],
      url: 'https://bingify.aldwiputra.site',
      type: 'web'
    },
    {
      title: 'Expenditura',
      imgPaths: ['/expenditura-onboard.webp', '/expenditura-home.webp', '/expenditura-dialog.webp'],
      techImgPaths: ['/android-icon.svg', '/kotlin-icon.svg', '/mysql-icon.svg'],
      url: 'https://github.com/DhewaGunawan/MoneyTrackerBinarPlatinum',
      type: 'mobile'
    },
    {
      title: 'Watchflix',
      imgPaths: ['/watchflix-home.webp', '/watchflix-detail.webp', '/watchflix-chat.webp'],
      techImgPaths: ['/android-icon.svg', '/kotlin-icon.svg', '/firebase-colored.svg'],
      url: 'https://github.com/DhewaGunawan/BinarWatchflix',
      type: 'mobile'
    },
    {
      title: 'RPS Game',
      imgPaths: ['/rps-splash.webp', '/rps-home.webp', '/rps-option.webp'],
      techImgPaths: ['/android-icon.svg', '/kotlin-icon.svg', '/db-icon.svg'],
      url: 'https://github.com/aldwiputra/rockpaperscissor-gui',
      type: 'mobile'
    }
  ];

  $: filteredProjects = projectsData.filter((project) => {
    if (activeTab === 'all') {
      return true;
    } else {
      return activeTab === 'mobile' ? project.type === 'mobile' : project.type === 'web';
    }
  });

  function handleChange(event: CustomEvent<{ state: Tab }>) {
    activeTab = event.detail.state;
  }
</script>

<section id="projects">
  <h2>Projects <span>.</span></h2>
  <div class="tab-buttons-container flex">
    <TabButton {activeTab} path="all-icon.svg" text="all" on:change={handleChange} />
    <TabButton {activeTab} path="webdev-icon.svg" text="web" on:change={handleChange} />
    <TabButton {activeTab} path="mobile-icon.svg" text="mobile" on:change={handleChange} />
  </div>
  <div class="projects-container">
    {#each filteredProjects as project}
      <Project
        title={project.title}
        imgPaths={project.imgPaths}
        techImgPaths={project.techImgPaths}
        url={project.url}
      />
    {/each}
  </div>
</section>

<style>
  section {
    margin-block-start: 10rem;
    margin-block-end: 7rem;
  }

  h2 {
    font-size: clamp(2rem, 5vw, 3rem);
    font-weight: 600;
  }

  span {
    color: var(--color-blue-400);
  }

  .tab-buttons-container {
    display: none;
    gap: 0.75rem;
    margin-block-start: 1.5rem;
  }

  @media screen and (min-width: 60rem) {
    section {
      margin-block-start: 7rem;
    }

    .tab-buttons-container {
      display: flex;
    }
  }
</style>
