<template>
  <section class="why-us">
    <div class="container">
      <h2 class="text-center">Why MintViralLabs?</h2>
      <p class="why-us__subtitle text-center">
        We make monetizing your TikTok/Instagram/Whatever audience easier than ever before.
      </p>
      
      <div class="benefits grid grid--2">
        <div class="benefit">
          <div class="benefit__icon"><span class="material-icons">attach_money</span></div>
          <h3>No commissions or hidden fees</h3>
          <p>You keep 100% of what we quote</p>
        </div>
        
        <div class="benefit">
          <div class="benefit__icon"><span class="material-icons">emoji_events</span></div>
          <h3>Bonus payments for overperformance</h3>
          <p>Exceed targets = extra cash</p>
        </div>
        
        <div class="benefit">
          <div class="benefit__icon"><span class="material-icons">groups</span></div>
          <h3>Perfect brand matches for your audience</h3>
          <p>No random crypto apps for cooking channels</p>
        </div>
        
        <div class="benefit">
          <div class="benefit__icon"><span class="material-icons">schedule</span></div>
          <h3>Flexible posting requirements</h3>
          <p>Hit your numbers however works best</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'WhyUs'
}
</script>

<style lang="scss" scoped>
@import '@/assets/styles/variables.scss';

.why-us {
  background-color: $background-color;
  
  &__subtitle {
    max-width: 600px;
    margin: 0 auto $spacing-xl;
    color: $light-text;
    font-size: 1.25rem;
  }
}

.benefits {
  margin-top: $spacing-xl;
}

.benefit {
  padding: $spacing-lg;
  background-color: $light-background;
  border-radius: $border-radius-lg;
  text-align: center;
  transition: transform 0.3s ease;
  
  &:hover {
    transform: translateY(-5px);
  }
  
  &__icon {
    font-size: 2.5rem;
    margin-bottom: $spacing-md;
    display: flex;
    justify-content: center;
    align-items: center;
    .material-icons {
      font-size: 2.5rem;
      color: $primary-color;
      vertical-align: middle;
    }
  }
  
  h3 {
    font-size: 1.25rem;
    margin-bottom: $spacing-sm;
    color: $text-color;
  }
  
  p {
    color: $light-text;
  }
}
</style> 