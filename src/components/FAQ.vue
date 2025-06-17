<template>
  <section id="faq" class="faq">
    <div class="container">
      <h2 class="text-center">FAQ</h2>
      <p class="faq__subtitle text-center">
        You've got questions, we've got the answers.
      </p>
      
      <div class="faq__list">
        <div v-for="(item, index) in faqItems" 
             :key="index" 
             class="faq-item"
             :class="{ 'is-active': activeIndex === index }">
          <div class="faq-item__header" @click="toggleItem(index)">
            <h3>{{ toTitleCase(item.question) }}</h3>
            <span class="faq-item__icon">+</span>
          </div>
          <div class="faq-item__content" v-show="activeIndex === index">
            <p>{{ item.answer }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'FAQ',
  data() {
    return {
      activeIndex: null,
      faqItems: [
        {
          question: 'Is this legit?',
          answer: '100% legit. Everything goes down in a proper contract with clear terms, payment schedules, and deliverables. You will get official invoicing, 1099s for taxes, and all the paperwork you would expect from a real business relationship. No recruiting friends, no buying starter kits, no weird pyramid schemes.'
        },
        {
          question: 'What if I do not hit my impression targets?',
          answer: 'Keep posting until you do. There is no time limit - some creators hit it in one viral post, others need the full month. As long as you are actively posting relevant content, you are golden.'
        },
        {
          question: 'How much can I actually make?',
          answer: 'On average, our starting contracts range from $800 to $1,500 / month. If you hit/exceed your goals, we will make sure to keep you happy! :)'
        },
        {
          question: 'What kind of apps will I be promoting?',
          answer: 'Currently, we are promoting 2 apps - one in the women\'s dating space, the other in the manifestation space. More to come over the next months.'
        },
        {
          question: 'Do you take a cut of my earnings?',
          answer: 'Nope. Zero commissions, zero fees. The rate we quote you is what hits your bank account'
        },
        {
          question: 'How long are the contracts?',
          answer: 'The contracts are month-to-month. Not happy with the partnership? No worries - you are not locked into anything.'
        },
        {
          question: 'Can I work with other brands while working with you?',
          answer: 'Absolutely. We just ask that you do not promote direct competitors during your contract period.'
        }
      ]
    }
  },
  methods: {
    toggleItem(index) {
      this.activeIndex = this.activeIndex === index ? null : index
    },
    toTitleCase(str) {
      return str.replace(/\w\S*/g, (txt) => txt.charAt(0).toUpperCase() + txt.substr(1).toLowerCase());
    }
  }
}
</script>

<style lang="scss" scoped>
@import '@/assets/styles/variables.scss';

.faq {
  background-color: $light-background;
  
  &__subtitle {
    max-width: 600px;
    margin: 0 auto $spacing-xl;
    color: $light-text;
    font-size: 1.25rem;
  }
  
  &__list {
    max-width: 800px;
    margin: 0 auto;
  }
}

.faq-item {
  background-color: $background-color;
  border-radius: $border-radius-md;
  margin-bottom: $spacing-md;
  overflow: hidden;
  
  &__header {
    padding: $spacing-lg;
    display: flex;
    justify-content: space-between;
    align-items: center;
    cursor: pointer;
    
    h3 {
      font-size: 1.125rem;
      margin: 0;
    }
  }
  
  &__icon {
    font-size: 1.5rem;
    color: $primary-color;
    transition: transform 0.3s ease;
  }
  
  &__content {
    padding: 0 $spacing-lg $spacing-lg;
    color: $light-text;
  }
  
  &.is-active {
    .faq-item__icon {
      transform: rotate(45deg);
    }
  }
}
</style> 