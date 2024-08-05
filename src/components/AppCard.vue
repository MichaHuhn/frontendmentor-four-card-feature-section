<script setup>
defineProps(['heading', 'description', 'iconSrc']);
</script>

<template>
  <article>
    <h2 class="heading">{{ heading }}</h2>
    <p class="description">{{ description }}</p>
    <img :src="iconSrc" alt="" class="icon">
  </article>
</template>

<style scoped lang="scss">
@import '@/styles/base/media-queries';

article {
  max-width: calc(350 / 16 * 1rem);
  aspect-ratio: 1.4;
  padding: 1.5rem 1.75rem 1.75rem calc(28 / 16 * 1rem);
  border-top: 3px solid var(--border-color);
  border-radius: 8px;
  box-shadow: 0 15px 30px -11px hsl(213deg 47% 67% / 0.5);
  display: flex;
  flex-direction: column;
  
  @media #{$laptop-and-bigger} {
    padding: calc(29 / 16 * 1rem) 2rem 2rem;
  }
  
  .heading {
    color: var(--color-very-dark-blue);
    font-size: 1.25rem;
    font-weight: 600;
  }
  
  .description {
    font-size: calc(13 / 16 * 1rem);
    line-height: calc(23 / 13);
    letter-spacing: 0.09px;
    
    @media #{$laptop-and-bigger} {
      margin-block-start: 0.375rem;
    }
  }
  
  .icon {
    width: calc(57 / 16 * 1rem);
    margin: auto 0 0 auto;
    
    @media #{$laptop-and-bigger} {
      width: 4rem;
    }
  }
}
</style>
