<template>
  <section id="how-it-works" class="how-it-works">
    <div class="container">
      <h2 class="text-center">Here's How This Works</h2>
      
      <div class="steps grid grid--2">
        <div class="step">
          <div class="step__number">1</div>
          <h3>Perfect Pairing</h3>
          <p>We pair you with an app that fits your channel's niche and audience perfectly</p>
        </div>
        
        <div class="step">
          <div class="step__number">2</div>
          <h3>Guaranteed Starting Rate</h3>
          <p>We give you a starting rate for X impressions (e.g., $1,000 for 500,000 impressions across 4 posts per month). The rate depends on your channel size, engagement, and location. No commissions or extra fees - you keep the whole sum.</p>
        </div>
        
        <div class="step">
          <div class="step__number">3</div>
          <h3>Flexible Delivery</h3>
          <p>Hit your impressions target with one reel? Awesome, that's a contract fulfilled. Otherwise, you keep posting until you reach that number.</p>
        </div>
        
        <div class="step">
          <div class="step__number">4</div>
          <h3>Bonus Rewards</h3>
          <p>Significantly exceed your impression target? You get a one-time bonus payment on top of your guaranteed rate.</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'HowItWorks'
}
</script>

<style lang="scss" scoped>
@import '@/assets/styles/variables.scss';

.how-it-works {
  background-color: $background-color;
}

.steps {
  margin-top: $spacing-xl;
}

.step {
  padding: $spacing-lg;
  background-color: $light-background;
  border-radius: $border-radius-lg;
  position: relative;
  
  &__number {
    position: absolute;
    top: -20px;
    left: $spacing-lg;
    width: 40px;
    height: 40px;
    background-color: $primary-color;
    color: white;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: bold;
    font-size: 1.25rem;
  }
  
  h3 {
    margin-top: $spacing-md;
    font-size: 1.5rem;
    color: $text-color;
  }
  
  p {
    color: $light-text;
    margin-top: $spacing-sm;
  }
}
</style> 