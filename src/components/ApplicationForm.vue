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
      
      <form 
        action="https://formsubmit.co/nickiamnot@gmail.com" 
        method="POST" 
        class="application-form"
      >
        <div class="form-group">
          <label for="name">Name</label>
          <input type="text" id="name" name="Name" required />
        </div>
        <div class="form-group">
          <label>Channel (pick ones that apply)</label>
          <div class="checkbox-group">
            <label class="checkbox">
              <input type="checkbox" name="Channel[]" value="TikTok" /> TikTok
            </label>
            <label class="checkbox">
              <input type="checkbox" name="Channel[]" value="Instagram" /> Instagram
            </label>
            <label class="checkbox">
              <input type="checkbox" name="Channel[]" value="YouTube" /> YouTube
            </label>
            <label class="checkbox">
              <input type="checkbox" name="Channel[]" value="YouTube Shorts" /> YouTube Shorts
            </label>
          </div>
        </div>
        <div class="form-group">
          <label for="channelLinks">Link your channels</label>
          <textarea id="channelLinks" name="Channel Links" required rows="3"></textarea>
        </div>
        <div class="form-group">
          <label for="location">Primary audience Location</label>
          <select id="location" name="Primary Audience Location" required>
            <option value="">Select a country</option>
            <option value="US">United States</option>
            <option value="CA">Canada</option>
            <option value="UK">United Kingdom</option>
            <option value="AU">Australia</option>
            <option value="OTHER">Other</option>
          </select>
        </div>
        <div class="form-group">
          <label for="niche">What's your niche?</label>
          <input type="text" id="niche" name="Niche" required />
        </div>
        <div class="form-group">
          <label for="email">Email (this is how we'll contact you)</label>
          <input type="email" id="email" name="Email" required />
        </div>
        <div class="form-group">
          <label for="followers">Total # of followers? (Approximation is fine!)</label>
          <input type="text" id="followers" name="Total Followers" required />
        </div>
        <div class="form-group">
          <label for="additional">Anything else we should know?</label>
          <textarea id="additional" name="Additional Info" rows="4"></textarea>
        </div>
        <button type="submit" class="btn btn--primary">Apply Now</button>
      </form>
    </div>
  </section>
</template>

<script>
export default {
  name: 'ApplicationForm'
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
button[type="submit"] {
  width: 100%;
  margin-top: $spacing-md;
}
</style> 