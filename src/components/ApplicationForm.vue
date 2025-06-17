<template>
  <section id="apply" class="application">
    <div class="container">
      <h2 class="text-center">Work with us!</h2>
      <p class="application__subtitle text-center">
        We're always on the lookout for fresh partners. Apply below 👇
      </p>
      <p class="application__note text-center">
        If we're a good match, we'll get back to you in 3-5 business days.
      </p>
      
      <form class="application-form" @submit.prevent="handleSubmit">
        <div class="form-group">
          <label for="name">Name</label>
          <input 
            type="text" 
            id="name" 
            v-model="form.name"
            required
            :class="{ 'has-error': errors.name }"
          />
          <span class="error-message" v-if="errors.name">{{ errors.name }}</span>
        </div>
        
        <div class="form-group">
          <label>Channel (pick ones that apply)</label>
          <div class="checkbox-group">
            <label class="checkbox">
              <input 
                type="checkbox" 
                v-model="form.channels" 
                value="TikTok"
              />
              TikTok
            </label>
            <label class="checkbox">
              <input 
                type="checkbox" 
                v-model="form.channels" 
                value="Instagram"
              />
              Instagram
            </label>
            <label class="checkbox">
              <input 
                type="checkbox" 
                v-model="form.channels" 
                value="YouTube"
              />
              YouTube
            </label>
            <label class="checkbox">
              <input 
                type="checkbox" 
                v-model="form.channels" 
                value="YouTube Shorts"
              />
              YouTube Shorts
            </label>
          </div>
          <span class="error-message" v-if="errors.channels">{{ errors.channels }}</span>
        </div>
        
        <div class="form-group">
          <label for="channelLinks">Link your channels</label>
          <textarea 
            id="channelLinks" 
            v-model="form.channelLinks"
            required
            rows="3"
            :class="{ 'has-error': errors.channelLinks }"
          ></textarea>
          <span class="error-message" v-if="errors.channelLinks">{{ errors.channelLinks }}</span>
        </div>
        
        <div class="form-group">
          <label for="location">Primary audience Location</label>
          <select 
            id="location" 
            v-model="form.location"
            required
            :class="{ 'has-error': errors.location }"
          >
            <option value="">Select a country</option>
            <option value="US">United States</option>
            <option value="CA">Canada</option>
            <option value="UK">United Kingdom</option>
            <option value="AU">Australia</option>
            <option value="OTHER">Other</option>
          </select>
          <span class="error-message" v-if="errors.location">{{ errors.location }}</span>
        </div>
        
        <div class="form-group">
          <label for="niche">What's your niche?</label>
          <input 
            type="text" 
            id="niche" 
            v-model="form.niche"
            required
            :class="{ 'has-error': errors.niche }"
          />
          <span class="error-message" v-if="errors.niche">{{ errors.niche }}</span>
        </div>
        
        <div class="form-group">
          <label for="email">Email (this is how we'll contact you)</label>
          <input 
            type="email" 
            id="email" 
            v-model="form.email"
            required
            :class="{ 'has-error': errors.email }"
          />
          <span class="error-message" v-if="errors.email">{{ errors.email }}</span>
        </div>
        
        <div class="form-group">
          <label for="followers">Total # of followers? (Approximation is fine!)</label>
          <input 
            type="text" 
            id="followers" 
            v-model="form.followers"
            required
            :class="{ 'has-error': errors.followers }"
          />
          <span class="error-message" v-if="errors.followers">{{ errors.followers }}</span>
        </div>
        
        <div class="form-group">
          <label for="additional">Anything else we should know?</label>
          <textarea 
            id="additional" 
            v-model="form.additional"
            rows="4"
          ></textarea>
        </div>
        
        <button type="submit" class="btn btn--primary">Apply Now</button>
      </form>
    </div>
  </section>
</template>

<script>
export default {
  name: 'ApplicationForm',
  data() {
    return {
      form: {
        name: '',
        channels: [],
        channelLinks: '',
        location: '',
        niche: '',
        email: '',
        followers: '',
        additional: ''
      },
      errors: {}
    }
  },
  methods: {
    validateForm() {
      this.errors = {}
      
      if (!this.form.name.trim()) {
        this.errors.name = 'Name is required'
      }
      
      if (this.form.channels.length === 0) {
        this.errors.channels = 'Please select at least one channel'
      }
      
      if (!this.form.channelLinks.trim()) {
        this.errors.channelLinks = 'Please provide your channel links'
      }
      
      if (!this.form.location) {
        this.errors.location = 'Please select your primary audience location'
      }
      
      if (!this.form.niche.trim()) {
        this.errors.niche = 'Please specify your niche'
      }
      
      if (!this.form.email.trim()) {
        this.errors.email = 'Email is required'
      } else if (!this.validateEmail(this.form.email)) {
        this.errors.email = 'Please enter a valid email address'
      }
      
      if (!this.form.followers.trim()) {
        this.errors.followers = 'Please provide your follower count'
      }
      
      return Object.keys(this.errors).length === 0
    },
    
    validateEmail(email) {
      const re = /^[^\s@]+@[^\s@]+\.[^\s@]+$/
      return re.test(email)
    },
    
    handleSubmit() {
      if (this.validateForm()) {
        // Here you would typically send the form data to your backend
        console.log('Form submitted:', this.form)
        alert('Thanks for applying! We will get back to you soon.')
        this.resetForm()
      }
    },
    
    resetForm() {
      this.form = {
        name: '',
        channels: [],
        channelLinks: '',
        location: '',
        niche: '',
        email: '',
        followers: '',
        additional: ''
      }
    }
  }
}
</script>

<style lang="scss" scoped>
@import '@/assets/styles/variables.scss';

.application {
  background-color: $background-color;
  
  &__subtitle {
    max-width: 600px;
    margin: 0 auto;
    color: $light-text;
    font-size: 1.25rem;
  }
  
  &__note {
    color: $light-text;
    margin-bottom: $spacing-xl;
  }
}

.application-form {
  max-width: 600px;
  margin: 0 auto;
  background-color: $light-background;
  padding: $spacing-xl;
  border-radius: $border-radius-lg;
}

.form-group {
  margin-bottom: $spacing-lg;
  
  label {
    display: block;
    margin-bottom: $spacing-xs;
    font-weight: 500;
  }
  
  input[type="text"],
  input[type="email"],
  select,
  textarea {
    width: 100%;
    padding: $spacing-sm;
    border: 1px solid darken($light-background, 10%);
    border-radius: $border-radius-sm;
    font-family: $font-primary;
    
    &:focus {
      outline: none;
      border-color: $primary-color;
    }
    
    &.has-error {
      border-color: #ef4444;
    }
  }
}

.checkbox-group {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: $spacing-sm;
  margin-top: $spacing-xs;
}

.checkbox {
  display: flex;
  align-items: center;
  gap: $spacing-xs;
  
  input[type="checkbox"] {
    width: 18px;
    height: 18px;
  }
}

.error-message {
  color: #ef4444;
  font-size: 0.875rem;
  margin-top: $spacing-xs;
  display: block;
}

button[type="submit"] {
  width: 100%;
  margin-top: $spacing-md;
}
</style> 