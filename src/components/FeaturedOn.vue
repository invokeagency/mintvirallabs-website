<template>
  <section class="featured">
    <div class="container">
      <div class="featured__grid">
        <a href="https://councils.forbes.com/profile/Nick-Zviadadze-Founder-MintSEO/5298272e-8c1e-48e9-9a04-3a3b098684a8" 
           target="_blank" 
           class="featured__item">
          <img src="@/assets/images/forbes.png" alt="Forbes" class="featured__logo" />
        </a>
        <a href="https://www.entrepreneur.com/author/nick-zviadadze" 
           target="_blank" 
           class="featured__item">
          <img src="@/assets/images/entreprenour_trans.png" alt="Entrepreneur" class="featured__logo" />
        </a>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'FeaturedOn'
}
</script>

<style lang="scss" scoped>
@import '@/assets/styles/variables.scss';

.featured {
  background-color: $light-background;
  padding: $spacing-lg 0;
  
  &__grid {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: $spacing-xl;
    flex-wrap: wrap;
  }
  
  &__item {
    opacity: 0.7;
    transition: opacity 0.3s ease;
    
    &:hover {
      opacity: 1;
    }
    
    .featured__logo {
      height: 50px;
      width: 200px;
      object-fit: contain;
      filter: grayscale(100%);
      transition: filter 0.3s ease;
      display: block;
      margin: 0 auto;
    }
    
    &:hover .featured__logo {
      filter: grayscale(0%);
    }
  }
}
</style> 