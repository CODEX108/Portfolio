<template>
    <div class="github-stats">
      <div class="stats-container">
        <img
          src="https://github-readme-stats.vercel.app/api?username=codex108&show_icons=true&private_count=true&theme=ambient_gradient"
          alt="GitHub Stats"
          class="stat-card"
        />
        <img
          src="https://github-readme-stats.vercel.app/api/top-langs?username=codex108&locale=en&hide_title=false&layout=compact&card_width=320&langs_count=6&theme=ambient_gradient&hide_border=false&order=2"
          alt="Top Languages"
          class="stat-card"
          height="190"
        />
        <picture class="stat-card">
          <source
            media="(prefers-color-scheme: dark)"
            :srcset="`https://streak-stats.demolab.com?user=codex108&theme=ambient_gradient`"
          />
          <img
            src="https://streak-stats.demolab.com?user=codex108&theme=default"
            alt="GitHub Streak"
          />
        </picture>
      </div>
      <div class="trophy-container">
        <picture class="trophy-card">
          <source
            media="(prefers-color-scheme: dark)"
            :srcset="`https://github-profile-trophy.vercel.app/?username=codex108&theme=radical&no-frame=false&no-bg=false&margin-w=9&margin-h=9`"
          />
          <img
            src="https://github-profile-trophy.vercel.app/?username=codex108&theme=radical&no-frame=false&no-bg=false&margin-w=10"
            alt="GitHub Trophies"
          />
        </picture>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'GithubStats',
  };
  </script>
  
  <style scoped lang="scss">
  .github-stats {
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 1.5rem;
  
    .stats-container {
      display: flex;
      justify-content: center;
      gap: 1rem;
      flex-wrap: wrap;
  
      .stat-card {
        border-radius: 0.5rem;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        padding: 1rem;
        background-color: var(--card-bg-color);
        color: var(--text-color);
      }
    }
  
    .trophy-container {
      display: flex;
      justify-content: center;
      margin-top: 1rem;
  
      .trophy-card {
        border-radius: 0.5rem;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        padding: 1rem;
        background-color: var(--card-bg-color);
        color: var(--text-color);
      }
    }
  
    @media (max-width: 900px) {
      padding: 1rem;
    }
  }
  </style>