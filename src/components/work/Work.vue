<script setup lang="ts">
  import Project from './Project.vue';

  interface project {
    title: string,
    role: string,
    year: string,
    summary: string,
    tags: string[]
  }

  const projects: project[] = [
    {
      title: 'Fyle',
      role: 'Frontend Engineering Intern',
      year: '2023',
      summary: 'Contributed to the ongoing development and upkeep of Fyle’s client-facing platform, delivering innovative solutions to streamline expense management processes and enhance user engagement.',
      tags: [
        'Angular', 'Jasmine', 'Ionic', 'Typescript'
      ]
    },
    {
      title: 'Diploma Tech Community',
      role: 'Open Source Manager',
      year: '2023',
      summary: "Collaborated with fellow students to build and contribute to several open-source projects",
      tags: [
        'React', 'Git', 'Github', 'Javascript'
      ]
    },
  ];
</script>

<template>
  <div id="work" class="page-section">
    <div class="work-col">
      <div id="work-summary">
        At Fyle, I improved system performance and user experience by overhauling key parts of the codebase. I spearheaded two major code coverage initiatives and strengthened the Angular codebase with rigorous unit testing.        <br /><br />
        <br /><br />
        In Mumbai, as part of Team Open Source at Diploma Tech Community, I collaborated on diverse open-source projects. My role included meticulous review of Pull Requests to uphold code quality and project standards.
      </div>
    </div>
    <div class="work-col">
      <div id="work-exp">
        <Project
          v-for="project in projects"
          :title="project.title"
          :role="project.role"
          :year="project.year"
          :summary="project.summary"
          :tags="project.tags"
        />
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
  #work {
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

    .work-col {
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

      #work-summary {
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

      #work-exp {
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