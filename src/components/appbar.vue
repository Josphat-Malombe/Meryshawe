<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'

const menuOpen = ref(false)
const activeDropdown = ref(null)

function toggleDropdown(name) {
  activeDropdown.value = activeDropdown.value === name ? null : name
}

function closeAllDropdowns() {
  activeDropdown.value = null
}

// close dropdowns when clicking outside
function handleClickOutside(e) {
  if (!e.target.closest('.dropdown')) {
    activeDropdown.value = null
  }
}

onMounted(() => {
  window.addEventListener('click', handleClickOutside)
})
onBeforeUnmount(() => {
  window.removeEventListener('click', handleClickOutside)
})
</script>

<template>
  <header class="appbar">
    <div class="nav-container">
      <div class="logo-section">
        <router-link to="/" class="logo-link">
          <img src="../assets/logo.jpg" alt="Merishaw School Logo" class="logo" />
          <span class="school-name"
            ><h4 style="font-weight: 900; font-size: 20px">Precious</h4>
            School</span
          >
        </router-link>
      </div>

      <nav :class="['nav-links', { open: menuOpen }]">
        <router-link to="/" class="nav-item">Home</router-link>

        <div class="dropdown">
          <span class="nav-item dropdown-toggle" @click.stop="toggleDropdown('about')">
            About Us ▾
          </span>
          <div class="dropdown-menu" v-if="activeDropdown === 'about'">
            <router-link to="/about/history">School History</router-link>
            <router-link to="/about/values">Mission & Vision</router-link>
            <router-link to="/about/administration">Administration</router-link>
            <router-link to="/about/board">Board</router-link>
          </div>
        </div>

        <div class="dropdown">
          <span class="nav-item dropdown-toggle" @click.stop="toggleDropdown('life')">
            School Life ▾
          </span>
          <div class="dropdown-menu" v-if="activeDropdown === 'life'">
            <router-link to="/life/student">Student Life</router-link>
            <router-link to="/life/clubs">Clubs & Societies</router-link>
            <router-link to="/life/sports">Sports</router-link>
            <router-link to="/life/extracurricular">Extracurricular Activities</router-link>
            <router-link to="/life/routine">Daily Routine</router-link>
          </div>
        </div>

        <div class="dropdown">
          <span class="nav-item dropdown-toggle" @click.stop="toggleDropdown('admissions')">
            Admissions ▾
          </span>
          <div class="dropdown-menu" v-if="activeDropdown === 'admissions'">
            <router-link to="/admissions/requirements">Admission Requirements</router-link>
            <router-link to="/admissions/process">Application Process</router-link>
            <router-link to="/admissions/fees">Fees Structure</router-link>
            <router-link to="/admissions/faq">FAQ</router-link>
          </div>
        </div>

        <div class="dropdown">
          <span class="nav-item dropdown-toggle" @click.stop="toggleDropdown('gallery')">
            Gallery ▾
          </span>
          <div class="dropdown-menu" v-if="activeDropdown === 'gallery'">
            <router-link to="/gallery/pictures">Pictures</router-link>
            <router-link to="/gallery/videos">Videos</router-link>
          </div>
        </div>

        <router-link :to="{ name: 'login' }" class="sign-in-btn">Sign In</router-link>
        <router-link :to="{ name: 'contact'}" class="contact">Contact Us</router-link>
      </nav>

      <button class="hamburger" @click="menuOpen = !menuOpen">
        <span :class="{ open: menuOpen }"></span>
        <span :class="{ open: menuOpen }"></span>
        <span :class="{ open: menuOpen }"></span>
      </button>
    </div>
  </header>
</template>

<style scoped>
.appbar {
  background-color: white;
  color: black;
  padding: 0.75rem 1.5rem;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15);
  z-index: 100;
  width: 100%;
  position: fixed;
  height: 80px;
}

.nav-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  max-width: 1440px;
  margin: 0 auto;
}

.logo-section {
  display: flex;
  align-items: center;
}

.logo-link {
  display: flex;
  align-items: center;
  text-decoration: none;
  color: black;
}

.logo {
  height: 65px;
  width: auto;
  margin-right: 0.6rem;
}

.school-name {
  font-weight: 600;
  font-size: 1.1rem;
  letter-spacing: 0.5px;
}

.nav-links {
  display: flex;
  gap: 1.5rem;
  align-items: center;
}

.nav-item {
  color: black;
  text-decoration: none;
  font-weight: 500;
  cursor: pointer;
  transition:
    color 0.3s,
    transform 0.2s;
}

.nav-item:hover {
  color: maroon;
  transform: translateY(-2px);
}

.dropdown {
  position: relative;
}

.dropdown-menu {
  position: absolute;
  top: 2.2rem;
  left: 0;
  background-color: white;
  border: 1px solid rgba(0, 0, 0, 0.1);
  border-radius: 6px;
  min-width: 180px;
  z-index: 200;
  display: flex;
  flex-direction: column;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.25);
}

.dropdown-menu router-link {
  color: black;
  padding: 0.6rem 1rem;
  text-decoration: none;
  display: block;
  transition: background-color 0.3s;
}

.dropdown-menu router-link:hover {
  background-color: #004080;
  color: #ffcc00;
}

.sign-in-btn {
  background-color: None;
  color: black;
  font-weight: 800;
  padding: 0.5rem 1rem;
  border-radius: 6px;
  text-decoration: none;
  transition:
    background-color 0.3s,
    transform 0.2s;
}

.sign-in-btn:hover {
  background-color: #095097;
  transform: translateY(-4px);
  color: white;
}
.contact {
  background-color: #095097;
  color: white;
  font-weight: 600;
  padding: 0.5rem 1rem;
  border-radius: 6px;
  text-decoration: none;
  transition:
    background-color 0.3s,
    transform 0.2s;
}
.hamburger {
  display: none;
  flex-direction: column;
  justify-content: center;
  align-items: flex-end;
  gap: 5px;
  background: none;
  border: none;
  cursor: pointer;
  width: 30px;
}

.hamburger span {
  display: block;
  width: 25px;
  height: 3px;
  background-color: black;
  border-radius: 2px;
  transition: all 0.3s ease;
}

.hamburger span.open:nth-child(1) {
  transform: rotate(45deg) translate(5px, 5px);
}

.hamburger span.open:nth-child(2) {
  opacity: 0;
}

.hamburger span.open:nth-child(3) {
  transform: rotate(-45deg) translate(6px, -6px);
}

@media (max-width: 900px) {
  .hamburger {
    display: flex;
  }

  .nav-links {
    position: absolute;
    top: 80px;
    right: 0;
    background-color: white;
    flex-direction: column;
    align-items: flex-start;
    padding: 1rem;
    gap: 1rem;
    width: 240px;
    display: none;
    border-radius: 0 0 8px 8px;
  }

  .nav-links.open {
    display: flex;
  }

  .dropdown-menu {
    position: static;
    box-shadow: none;
    border: none;
    background: none;
  }

  .dropdown-menu router-link {
    padding: 0.4rem 0.8rem;
  }
}
</style>
