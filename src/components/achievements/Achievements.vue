<script setup lang="ts">
  import Achievement from './Achievement.vue';

  interface Achievement {
    title: string,
    award: string,
    year: string,
    description: string,
    participants?: string,
    show: boolean
  }

  const achievements: Achievement[] = [
    {
      title: 'ScrollHacks Global Hackathon',
      award: 'Best Beginner Team & Orkes Track Winner',
      year: 'September 2024',
      description: 'Achieved "Best Beginner Team" award in the Open Innovation Track among over 500+ participants. Winner of the Orkes Track for demonstrating innovative use of platform services and optimization techniques.',
      participants: '500+',
      show: true,
    },
    {
      title: 'Nomura KakushIN Finalist',
      award: 'Top 30 Finalist',
      year: 'July 2025',
      description: 'Among 600+ applicants, was a finalist in the hackathon demonstrating exceptional technical skills and innovation.',
      participants: '600+',
      show: true,
    },
  ];
</script>

<template>
  <div id="achievements" class="page-section">
    <div class="achievements-col">
      <div id="achievements-summary">
        Recognition for technical excellence and innovation across various competitive platforms. These achievements reflect my commitment to continuous learning and delivering impactful solutions.

        <br /><br />

        Achievement roadmap &#8594;
      </div>
    </div>
    <div class="achievements-col">
      <div id="achievements-roadmap">
        <div class="timeline">
          <Achievement
            v-for="(achievement, index) in achievements"
            :key="index"
            :show="achievement.show"
            :title="achievement.title"
            :award="achievement.award"
            :year="achievement.year"
            :description="achievement.description"
            :participants="achievement.participants"
            :index="index"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
  #achievements {
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

    .achievements-col {
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

      #achievements-summary {
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

      #achievements-roadmap {
        position: relative;

        .timeline {
          position: relative;
          
          &::before {
            content: '';
            position: absolute;
            left: 2rem;
            top: 0;
            bottom: 0;
            width: 2px;
            background: linear-gradient(to bottom, var(--border), transparent);
            z-index: 1;

            @media only screen and (max-width: 900px) {
              left: 1rem;
            }
          }
        }
      }
    }
  }
</style>
