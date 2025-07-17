<script setup lang="ts">
import SideProject from './SideProject.vue';
  interface side_project {
    title: string,
    type: string,
    href: string,
    image_url: string,
    tags: string[],
    show: boolean
  }

  const side_projects: side_project[] = [
  {
      title: 'Shrimad Bhagvad Gita',
      type: 'Android App',
      href: 'https://github.com/CODEX108/Shrimad-Bhagvad-Gita',
      image_url: 'side-projects/sbg.jpeg',
      tags: [
        'Android',
        'Java',
        'Firebase'
      ],
      show: true,
    },
    {
      title: 'MemoryBox',
      type: 'Web App',
      href: 'https://github.com/CODEX108/TheMemoryBox',
      image_url: 'side-projects/memoryBox.png',
      tags: [
        'Next.js',
        'NeonDB',
        'Drizzle ORM'
      ],
      show: true,
    },
     {
      title: 'BlockSpirit',
      type: 'DApp',
      href: 'https://github.com/CODEX108/FINAL-BLOCKSPIRIT',
      image_url: 'side-projects/blockspirit.jpeg',
      tags: [
        'Solidity',
        'React',
        'Hardhat',
        'Ethers.js',
      ],
      show: true,
    },
    {
      title: 'RippleFeed',
      type: 'Web App',
      href: 'https://github.com/CODEX108/RippleFeed',
      image_url: 'side-projects/ripplefeed.jpeg',
      tags: [
        'Next JS',
        'Prisma',
        'Tailwind CSS'
      ],
      show: true,
    },
  ];
</script>

<template>
  <div id="side-projects" class="page-section">
    <div class="side-projects-col">
      <div id="sp-summary">
        I have a passion for creating dynamic solutions. My projects are a testament to this. I have worked on a variety of projects ranging from DApps to Android apps. I am always looking for new projects to work on. If you have a project in mind, feel free to reach out to me.

        <br /><br />

        Select projects &#8594;
      </div>
    </div>
    <div class="side-projects-col">
      <div id="side-projects-exp">
        <SideProject
          v-for="project in side_projects"
          :show="project.show"
          :title="project.title"
          :type="project.type"
          :href="project.href"
          :image_url="project.image_url"
          :tags="project.tags"
        />
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
  #side-projects {
    display: -ms-grid;
    display: grid;
    grid-template-columns: 1fr 1fr;
    border-bottom: 1px solid var(--border);
    -webkit-transition: border .3s ease;
    -o-transition: border .3s ease;
    transition: border .3s ease;

    @media only screen and (max-width: 900px) {
      grid-template-columns: 1fr;
    }

    .side-projects-col {
      padding: 5rem;

      &:nth-of-type(1) {
        @media only screen and (max-width: 900px) {
          padding-bottom: 0;
        }
      }

      @media only screen and (max-width: 900px) {
        padding: 1rem;
      }

      &:first-child {
        border-right: 1px solid var(--border);
        -webkit-transition: border .3s ease;
        -o-transition: border .3s ease;
        transition: border .3s ease;

        @media only screen and (max-width: 900px) {
          border: none;
        }
      }

      #sp-summary {
        -webkit-box-flex: 4;
        -ms-flex: 4;
        flex: 4;
        font-size: 1.25rem;
        font-weight: 300;
        position: sticky;
        top: 5rem;

        @media only screen and (max-width: 900px) {
          position: unset;
        }
      }

      #side-projects-exp {
        display: -ms-grid;
        display: grid;
        gap: 5rem;

        @media only screen and (max-width: 900px) {
          gap: 1rem;
        }
      }
    }
  }
</style>