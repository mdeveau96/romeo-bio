<template>
  <div class="bio-container">
    <div class="profile-section">
      <img :src="profileImage" alt="Profile Picture" class="profile-image" />
      <h1>{{ name }}</h1>
      <h2>{{ title }}</h2>
    </div>

    <div class="bio-section">
      <h3>About Me</h3>
      <p>
        Yes, I know—I look a little rough. But don’t worry, I’m not lost or
        dying! I have a diagnosed skin condition and
        <strong>FIV (feline immunodeficiency virus)</strong>, which makes me
        look a bit worse than I feel.
      </p>
      <img :src="sickImage" alt="Profile Picture" class="sick-image" />
      <p>
        My family knows all about it, and
        <strong>I’ve been treated by a vet.</strong> I get love, care, and
        plenty of food at home—I just like to wander! So if you see me around
        the neighborhood, please don’t worry. I belong to a loving home and I’m
        doing okay, even if my fur doesn’t always look that way.💛
      </p>
      <p>Thanks for looking out for me!</p>
      <p>— Romeo the Outdoor Adventurer</p>
    </div>

    <div class="contact-section">
      <h3>If you have any questions about me:</h3>
      <ul>
        <li v-for="(contact, index) in contacts" :key="index">
          <strong>{{ contact.type }}:</strong> {{ contact.value }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const profileImage = ref("/romeo.jpg");
const sickImage = ref("/romeo-sick.png");
const name = ref("Hi, I'm Romeo! 🐾");
const contacts = ref([
  { type: "Email", value: "lauraramirezlovespies123453@gmail.com" },
]);
</script>

<style scoped>
@keyframes slideUp {
  from {
    transform: translateY(100vh);
    opacity: 0;
  }
  to {
    transform: translateY(0);
    opacity: 1;
  }
}

.bio-container {
  max-width: 800px;
  margin: 0 auto;
  padding: 2rem;
  animation: slideUp 1s ease-out;
}

.profile-section {
  text-align: center;
  margin-bottom: 2rem;
}

.profile-image {
  width: 300px;
  height: 300px;
  object-fit: cover;
  object-position: center 20%;
  border-radius: 400px;
  margin-bottom: 1rem;
}

.sick-image {
  width: 300px;
  height: 300px;
  object-fit: cover;
  object-position: 0% 20%;
  border-radius: 400px;
  margin-bottom: 1rem;
}

.bio-section,
.contact-section {
  margin-bottom: 2rem;
}

h1 {
  color: #2c3e50;
  margin-bottom: 0.5rem;
}

h2 {
  color: #7f8c8d;
  font-weight: normal;
  margin-bottom: 1.5rem;
}

h3 {
  color: #34495e;
  margin-bottom: 1rem;
}

ul {
  list-style: none;
  padding: 0;
}

li {
  margin-bottom: 0.5rem;
}

p {
  line-height: 1.6;
  color: #2c3e50;
}
</style>
