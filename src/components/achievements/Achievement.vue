<script setup lang="ts">
  defineProps(['title', 'award', 'year', 'description', 'participants', 'show', 'index']);
</script>

<template>
  <div
    class="achievement-timeline-item"
    v-if="show"
  >
    <div class="timeline-marker">
      <div class="timeline-dot"></div>
    </div>
    <div class="achievement-card" :class="`achievement-${index}`">
      <div class="achievement-header">
        <div class="achievement-title">{{ title }}</div>
        <div class="achievement-year">{{ year }}</div>
      </div>
      <div class="achievement-award">{{ award }}</div>
      <div class="achievement-description">{{ description }}</div>
      <div class="achievement-participants" v-if="participants">
        <div class="participants-badge">{{ participants }} participants</div>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
  .achievement-timeline-item {
    position: relative;
    margin-bottom: 3rem;
    display: flex;
    align-items: flex-start;
    gap: 2rem;

    @media only screen and (max-width: 900px) {
      gap: 1rem;
      margin-bottom: 2rem;
    }

    .timeline-marker {
      position: relative;
      z-index: 2;
      margin-top: 1.5rem;

      .timeline-dot {
        width: 16px;
        height: 16px;
        background: var(--border);
        border-radius: 50%;
        border: 3px solid var(--bg);
        box-shadow: 0 0 0 3px var(--border);
      }
    }

    .achievement-card {
      color: #000;
      border-radius: .75rem;
      display: grid;
      gap: 1rem;
      font-size: 1.25rem;
      font-weight: 300;
      padding: 2rem;
      flex: 1;
      box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
      border: 2px solid rgba(255, 255, 255, 0.2);

      @media only screen and (max-width: 900px) {
        padding: 1.5rem;
      }

      // ScrollHacks - Green gradient
     // ScrollHacks - Enhanced Green Gradient
&.achievement-0 {
  background: linear-gradient(
    135deg,
    #4ade80 0%,      // Light green
    #22c55e 25%,     // Medium green
    #166534 50%,     // Dark green
    #064e3b 70%,     // Bottle green
    #16a34a 100%     // Rich green
  );
  color: white;
}


      // Nomura - Red gradient  
      // Nomura - Enhanced Red Gradient  
&.achievement-1 {
  background: linear-gradient(
    135deg,
    #f97316 0%,      // Orange
    #ef4444 20%,     // Bright red
    #dc2626 45%,     // Medium red
    #991b1b 75%,     // Dark red
    #7f1d1d 100%     // Deeper dark red
  );
  color: white;

}


      .achievement-header {
        display: flex;
        justify-content: space-between;
        align-items: flex-start;
        gap: 1rem;

        @media only screen and (max-width: 900px) {
          flex-direction: column;
          gap: 0.5rem;
        }

        .achievement-title {
          font-weight: 700;
          font-size: 1.5rem;
          flex: 1;
          line-height: 1.2;
        }

        .achievement-year {
          font-weight: 600;
          font-size: 1rem;
          opacity: 0.9;
          white-space: nowrap;
          background: rgba(255, 255, 255, 0.2);
          padding: 0.25rem 0.75rem;
          border-radius: 1rem;
        }
      }

      .achievement-award {
        font-weight: 600;
        font-size: 1.1rem;
        opacity: 0.95;
        background: rgba(255, 255, 255, 0.15);
        padding: 0.5rem 1rem;
        border-radius: 0.5rem;
        display: inline-block;
        max-width: fit-content;
      }

      .achievement-description {
        font-size: 1rem;
        line-height: 1.6;
        opacity: 0.85;
      }

      .achievement-participants {
        display: flex;
        justify-content: flex-end;

        .participants-badge {
          background: rgba(0, 0, 0, 0.15);
          padding: 0.5rem 1rem;
          border-radius: 1.5rem;
          font-size: 0.9rem;
          font-weight: 600;
          max-width: fit-content;
        }
      }
    }
  }
</style>
