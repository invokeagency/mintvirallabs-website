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
              <span class="platform__label">TikTok</span>
            </div>
            <div class="platform">
              <img src="@/assets/images/instagram.svg" alt="Instagram" />
              <span class="platform__label">Instagram</span>
            </div>
            <div class="platform">
              <img src="@/assets/images/youtube.svg" alt="YouTube" />
              <span class="platform__label">YouTube</span>
            </div>
            <div class="platform">
              <svg width="40" height="40" viewBox="0 0 40 40" fill="none" xmlns="http://www.w3.org/2000/svg">
                <rect x="7.5" y="10" width="25" height="20" rx="5" stroke="#1f2937" stroke-width="2"/>
                <polygon points="22,20 17,23 17,17" fill="#1f2937"/>
                <rect x="28" y="15" width="3" height="10" rx="1.5" fill="#FF0000"/>
              </svg>
              <span class="platform__label">Shorts</span>
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
    font-size: 1.2rem;
  }
  
  &__grid {
    display: flex;
    justify-content: center;
    gap: $spacing-xl;
    flex-wrap: wrap;
  }
}

.platform {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: $spacing-xs;
  img, svg {
    height: 40px;
    width: 40px;
    margin-bottom: 0.2rem;
    transition: transform 0.2s;
  }
  &:hover img, &:hover svg {
    transform: scale(1.12);
  }
  &__label {
    font-size: 0.95rem;
    color: $text-color;
    margin-top: 0.1rem;
    font-weight: 500;
    letter-spacing: 0.01em;
  }
}
</style> 