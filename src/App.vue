<script setup>
import AppCard from '@/components/AppCard.vue';
import SupervisorIcon from '@/assets/icons/supervisor.svg';
import TeamBuilderIcon from '@/assets/icons/team-builder.svg';
import KarmaIcon from '@/assets/icons/karma.svg';
import CalculatorIcon from '@/assets/icons/calculator.svg';
</script>

<template>
  <header>
    <div class="max-width-wrapper">
      <h1>
        Reliable, efficient delivery
        <br>
        <strong>Powered by Technology</strong>
      </h1>
      <p class="description">
        Our Artificial Intelligence powered tools use millions of project data points
        to ensure that your project is successful
      </p>
    </div>
  </header>
  
  <main>
    <div class="cards-layout spacing-wrapper">
      <div class="column">
        <AppCard
          heading="Supervisor"
          description="Monitors activity to identify project roadblocks"
          :icon-src="SupervisorIcon"
          style="--border-color: var(--color-cyan)"
        />
      </div>
      <div class="column center-column">
        <AppCard
          heading="Team Builder"
          description="Scans our talent network to create the optimal team for your project"
          :icon-src="TeamBuilderIcon"
          style="--border-color: var(--color-red)"
        />
        <AppCard
          heading="Karma"
          description="Regularly evaluates our talent to ensure quality"
          :icon-src="KarmaIcon"
          style="--border-color: var(--color-orange)"
        />
      </div>
      <div class="column">
        <AppCard
          heading="Calculator"
          description="Uses data from past projects to provide better delivery estimates"
          :icon-src="CalculatorIcon"
          style="--border-color: var(--color-blue)"
        />
      </div>
    </div>
  </main>
</template>

<style scoped lang="scss">
@import '@/styles/base/media-queries';

header {
  margin-block-end: calc(76 / 16 * 1rem);
  text-align: center;
  
  @media #{$laptop-and-bigger} {
    margin-block-end: 4rem;
  }
  
  h1 {
    color: var(--color-very-dark-blue);
    font-size: 1.5rem;
    font-weight: 200;
    line-height: 1.425;
    letter-spacing: 0.17px;
    
    @media #{$laptop-and-bigger} {
      font-size: 2.25rem;
    }
    
    strong {
      font-weight: 600;
    }
  }
  
  .description {
    margin-block-start: calc(13 / 16 * 1rem);
    line-height: calc(25 / 15);
    letter-spacing: 0.1px;
  }
}

main {
  display: flex;
  justify-content: center;
  
  .cards-layout {
    --gap: calc(25 / 16 * 1rem);
    
    display: grid;
    gap: var(--gap);
    
    @media #{$laptop-and-bigger} {
      --gap: calc(30 / 16 * 1rem);
      
      grid-template-columns: 1fr 1fr 1fr;
      align-items: center;
    }
    
    > * {
      flex: 1;
    }
    
    .center-column {
      display: flex;
      flex-direction: column;
      gap: var(--gap);
    }
  }
}

.max-width-wrapper {
  --content-max-width: 33.75rem;
  --spacing-inline: 2rem;
  
  width: min(var(--content-max-width), 100% - (var(--spacing-inline) * 2));
  margin-inline: auto;
}

.spacing-wrapper {
  --spacing-inline: 2rem;
  
  max-width: calc(100% - (var(--spacing-inline) * 2));
  margin-inline: auto;
}

:global(body) {
  padding-block: calc(82 / 16 * 1rem);
}
</style>
