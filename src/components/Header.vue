<template>
  <header class="header">
    <nav class="nav container">
      <div class="nav__logo">
        <img src="@/assets/images/logo.svg" alt="MintViralLabs" />
      </div>
      <div class="nav__menu">
        <a href="#how-it-works" class="nav__link">How It Works</a>
        <a href="#team" class="nav__link">Our Team</a>
        <a href="#faq" class="nav__link">FAQ</a>
        <a href="#apply" class="btn btn--primary">Apply Now</a>
      </div>
    </nav>

    <div class="hero container">
      <div class="hero__content">
        <h1>We help online content creators monetize their brand</h1>
        <p class="hero__subtitle">
          Get matched with perfect brand partners and earn predictable income every month.
        </p>
        <a href="#apply" class="btn btn--primary">Apply to Work With Us</a>
        
        <div class="platforms">
          <p>We work with creators on all platforms:</p>
          <div class="platforms__grid">
            <div class="platform">
              <img src="@/assets/images/tiktok.svg" alt="TikTok" />
              <span>✅</span>
            </div>
            <div class="platform">
              <img src="@/assets/images/instagram.svg" alt="Instagram" />
              <span>✅</span>
            </div>
            <div class="platform">
              <img src="@/assets/images/youtube.svg" alt="YouTube" />
              <span>✅</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: 'HeaderSection'
}
</script>

<style lang="scss" scoped>
@import '@/assets/styles/variables.scss';

.header {
  padding-top: $spacing-md;
  background: linear-gradient(to bottom, $light-background, $background-color);
}

.nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: $spacing-md 0;
  
  &__logo {
    img {
      height: 40px;
    }
  }
  
  &__menu {
    display: flex;
    gap: $spacing-lg;
    align-items: center;
  }
  
  &__link {
    color: $text-color;
    text-decoration: none;
    font-weight: 500;
    
    &:hover {
      color: $primary-color;
    }
  }
}

.hero {
  padding: $spacing-xl 0;
  text-align: center;
  
  &__content {
    max-width: 800px;
    margin: 0 auto;
  }
  
  &__subtitle {
    font-size: 1.25rem;
    color: $light-text;
    margin-bottom: $spacing-lg;
  }
}

.platforms {
  margin-top: $spacing-xl;
  
  p {
    margin-bottom: $spacing-md;
    font-weight: 500;
  }
  
  &__grid {
    display: flex;
    justify-content: center;
    gap: $spacing-lg;
  }
}

.platform {
  position: relative;
  
  img {
    height: 40px;
    width: 40px;
  }
  
  span {
    position: absolute;
    bottom: -10px;
    right: -10px;
    font-size: 1.25rem;
  }
}
</style> 