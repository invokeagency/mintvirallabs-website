<template>
  <section id="team" class="team">
    <div class="container">
      <h2 class="text-center">A team you'll love working with</h2>
      <p class="team__subtitle text-center">
        No corporate robots. Just a small team of real humans who answer DMs, hop on calls, and won't ghost you after you sign.
      </p>
      
      <div class="team__grid grid grid--3">
        <div class="team-member" v-for="member in members" :key="member.name">
          <img :src="member.img" :alt="member.name" class="team-member__image" />
          <h3 class="team-member__name">{{ member.name }}</h3>
          <div class="team-member__role">{{ member.role }}</div>
          <div v-if="member.socials" class="team-member__socials">
            <a v-for="social in member.socials" :key="social.url" :href="social.url" target="_blank" rel="noopener" class="team-member__social-link">
              <img :src="social.icon" :alt="social.label" />
              <span class="sr-only">{{ social.label }}</span>
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'TeamSection',
  data() {
    return {
      members: [
        {
          name: 'Sidonja Manushi',
          role: 'Head of Content',
          desc: 'Visionary founder, always on the lookout for new ways to help creators thrive online.',
          img: require('@/assets/images/team/sidonja_manushi.avif')
        },
        {
          name: 'Nick Zviadadze',
          role: 'Founder & Manager',
          desc: 'Leads our vision and ensures creators get the best brand deals.',
          img: require('@/assets/images/team/nick.avif'),
          socials: [
            {
              label: 'Twitter',
              url: 'https://x.com/Nick_zv_',
              icon: require('@/assets/images/twitter.svg')
            },
            {
              label: 'LinkedIn',
              url: 'https://www.linkedin.com/in/nickzviadadze/',
              icon: require('@/assets/images/linkedin.svg')
            }
          ]
        },
        {
          name: 'Mina Pavlović',
          role: 'Content Specialist',
          desc: 'Creates content that connects brands and audiences.',
          img: require('@/assets/images/team/mina.avif')
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
@import '@/assets/styles/variables.scss';
.team {
  background-color: $light-background;
  
  &__subtitle {
    max-width: 600px;
    margin: 0 auto $spacing-xl;
    color: $light-text;
    font-size: 1.25rem;
  }
  
  &__grid {
    margin-top: $spacing-xl;
  }
}

.grid--3 {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: $spacing-xl;
  @media (max-width: $desktop) {
    grid-template-columns: repeat(2, 1fr);
  }
  @media (max-width: $tablet) {
    grid-template-columns: 1fr;
  }
}

.team-member {
  text-align: center;
  
  &__image {
    width: 160px;
    height: 160px;
    border-radius: 50%;
    object-fit: cover;
    margin-bottom: $spacing-md;
    background: $background-color;
    border: 2px solid $light-text;
  }
  
  &__name {
    font-size: 1.25rem;
    font-weight: 700;
    margin-bottom: $spacing-xs;
    color: $text-color;
  }
  
  &__role {
    color: $light-text;
    margin-bottom: $spacing-xs;
    font-weight: 600;
    font-size: 1rem;
  }
  
  &__desc {
    color: $text-color;
    font-size: 0.98rem;
    margin-bottom: $spacing-sm;
    min-height: 2.5em;
    line-height: 1.4;
  }
  
  &__socials {
    margin-top: $spacing-xs;
    display: flex;
    justify-content: center;
    gap: $spacing-md;
  }
  
  &__social-link {
    display: inline-flex;
    align-items: center;
    img {
      width: 28px;
      height: 28px;
      opacity: 0.7;
      transition: opacity 0.2s;
    }
    &:hover img {
      opacity: 1;
    }
  }
}

.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0,0,0,0);
  border: 0;
}
</style> 