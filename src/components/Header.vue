<template>
  <header class="header" :class="{ 'scrolled': hasScrolled }">
    <div class="container">
      <!-- Logo section -->
      <div class="logo">
        <router-link to="/">
          <img src="/assets/logos/lenergy-logo.svg" alt="Lenergy Logo" height="40" />
        </router-link>
      </div>
      
      <!-- Navigation menu -->
      <nav class="nav" :class="{ 'active': isMobileMenuOpen }">
        <ul>
          <li><router-link to="/" @click="closeMobileMenu">Home</router-link></li>
          
          <!-- Products dropdown menu -->
          <li class="dropdown">
            <a @click.prevent="toggleProductsDropdown" href="#" class="dropdown-toggle">
              Products
              <span class="dropdown-icon" :class="{ 'open': isProductsDropdownOpen }">
                <svg xmlns="http://www.w3.org/2000/svg" width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <polyline points="6 9 12 15 18 9"></polyline>
                </svg>
              </span>
            </a>
            <ul class="dropdown-menu" v-show="isProductsDropdownOpen">
              <li><router-link to="/products/industrial" @click="closeMobileMenu">Industrial Hoses</router-link></li>
              <li><router-link to="/products/oil-and-gas" @click="closeMobileMenu">Oil & Gas Hoses</router-link></li>
              <li><router-link to="/products/food-beverage" @click="closeMobileMenu">Food & Beverage Hoses</router-link></li>
              <li><router-link to="/products/chemical" @click="closeMobileMenu">Chemical Hoses</router-link></li>
              <li><router-link to="/products/fittings" @click="closeMobileMenu">Fittings & Couplings</router-link></li>
              <li><router-link to="/products" @click="closeMobileMenu">All Products</router-link></li>
            </ul>
          </li>
          
          <li><router-link to="/about" @click="closeMobileMenu">About Us</router-link></li>
          <li><router-link to="/contact" @click="closeMobileMenu">Contact</router-link></li>
        </ul>
      </nav>
      
      <!-- Call to action button -->
      <div class="header-cta">
        <router-link to="/contact" class="cta-button">Get a Quote</router-link>
      </div>
      
      <!-- Mobile menu toggle button -->
      <div class="mobile-menu-toggle" @click="toggleMobileMenu">
        <span :class="{ 'open': isMobileMenuOpen }"></span>
        <span :class="{ 'open': isMobileMenuOpen }"></span>
        <span :class="{ 'open': isMobileMenuOpen }"></span>
      </div>
    </div>
  </header>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

// Reactive state for menu toggles
const isMobileMenuOpen = ref(false);
const isProductsDropdownOpen = ref(false);
const hasScrolled = ref(false);

// Function to toggle mobile menu
const toggleMobileMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value;
  
  // Close dropdown when mobile menu is toggled
  if (!isMobileMenuOpen.value) {
    isProductsDropdownOpen.value = false;
  }
};

// Function to toggle products dropdown
const toggleProductsDropdown = () => {
  isProductsDropdownOpen.value = !isProductsDropdownOpen.value;
};

// Function to close mobile menu (for navigation links)
const closeMobileMenu = () => {
  isMobileMenuOpen.value = false;
  isProductsDropdownOpen.value = false;
};

// Handle scroll effect for header
const handleScroll = () => {
  hasScrolled.value = window.scrollY > 50;
};

// Add scroll event listener when component is mounted
onMounted(() => {
  window.addEventListener('scroll', handleScroll);
});

// Remove scroll event listener when component is unmounted
onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
});
</script>

<style scoped>
/* Header styles with Dark Slate and Red color palette */
.header {
  background-color: #2c3e50; /* Dark slate blue base */
  color: white;
  padding: 1.2rem 0;
  position: sticky;
  top: 0;
  z-index: 100;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  width: 100%;
  transition: all 0.3s ease;
}

.header.scrolled {
  background-color: rgba(44, 62, 80, 0.95);
  padding: 0.8rem 0;
  box-shadow: 0 2px 20px rgba(0, 0, 0, 0.2);
}

.container {
  max-width: 1200px;
  width: 100%;
  margin: 0 auto;
  padding: 0 1rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo img {
  height: 60px;
  transition: transform 0.3s;
}

.logo img:hover {
  transform: scale(1.05);
}

.nav ul {
  display: flex;
  list-style: none;
  margin: 0;
  padding: 0;
}

.nav li {
  margin-left: 2.5rem;
  position: relative;
}

.nav a {
  color: white;
  text-decoration: none;
  font-weight: 500;
  padding: 0.5rem 0;
  transition: all 0.3s;
  position: relative;
  display: block;
}

.nav a:hover,
.nav a.router-link-active {
  color: #e74c3c; /* Red accent */
}

.nav a::after {
  content: '';
  position: absolute;
  width: 0;
  height: 2px;
  bottom: 0;
  left: 0;
  background-color: #e74c3c; /* Red accent */
  transition: width 0.3s;
}

.nav a:hover::after,
.nav a.router-link-active::after {
  width: 100%;
}

/* Dropdown styling */
.dropdown {
  position: relative;
}

.dropdown-toggle {
  cursor: pointer;
  display: flex;
  align-items: center;
}

.dropdown-icon {
  margin-left: 0.3rem;
  transition: transform 0.3s;
}

.dropdown-icon.open {
  transform: rotate(180deg);
}

.dropdown-menu {
  position: absolute;
  top: 100%;
  left: -1rem;
  background-color: #2c3e50; /* Dark slate blue base */
  min-width: 220px;
  padding: 0.8rem 0;
  border-radius: 0 0 4px 4px;
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.15);
  z-index: 200;
  opacity: 0;
  transform: translateY(10px);
  animation: fadeIn 0.3s forwards;
}

@keyframes fadeIn {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.dropdown-menu li {
  margin: 0;
}

.dropdown-menu a {
  padding: 0.6rem 1.2rem;
  display: block;
}

.dropdown-menu a:hover {
  background-color: #34495e; /* Slightly lighter slate for hover */
}

.dropdown-menu a::after {
  display: none;
}

/* CTA Button */
.header-cta {
  margin-left: 2rem;
}

.cta-button {
  background-color: #e74c3c; /* Red accent */
  color: white;
  padding: 0.6rem 1.2rem;
  border-radius: 3px;
  font-weight: 500;
  transition: all 0.3s;
  text-decoration: none;
  display: inline-block;
}

.cta-button:hover {
  background-color: #c0392b; /* Darker red on hover */
  transform: translateY(-2px);
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.15);
}

/* Mobile menu toggle */
.mobile-menu-toggle {
  display: none;
  flex-direction: column;
  justify-content: space-between;
  width: 30px;
  height: 20px;
  cursor: pointer;
  z-index: 201;
}

.mobile-menu-toggle span {
  display: block;
  height: 2px;
  width: 100%;
  background-color: white;
  transition: all 0.3s ease-in-out;
  transform-origin: center;
}

.mobile-menu-toggle span.open:nth-child(1) {
  transform: translateY(9px) rotate(45deg);
}

.mobile-menu-toggle span.open:nth-child(2) {
  opacity: 0;
}

.mobile-menu-toggle span.open:nth-child(3) {
  transform: translateY(-9px) rotate(-45deg);
}

/* Responsive styles */
@media (max-width: 992px) {
  .nav li {
    margin-left: 1.5rem;
  }
}

@media (max-width: 768px) {
  .mobile-menu-toggle {
    display: flex;
  }
  
  .nav {
    position: fixed;
    top: 0;
    right: 0;
    bottom: 0;
    width: 80%;
    max-width: 320px;
    background-color: #2c3e50;
    transform: translateX(100%);
    transition: transform 0.3s ease-in-out;
    padding: 4rem 0 0;
    z-index: 200;
    box-shadow: -5px 0 15px rgba(0, 0, 0, 0.1);
    overflow-y: auto;
  }
  
  .nav.active {
    transform: translateX(0);
  }
  
  .nav ul {
    flex-direction: column;
    padding: 0;
  }
  
  .nav li {
    margin: 0;
    width: 100%;
    border-bottom: 1px solid rgba(255, 255, 255, 0.1);
  }
  
  .nav a {
    padding: 1rem 2rem;
  }
  
  .dropdown-menu {
    position: static;
    width: 100%;
    box-shadow: none;
    border-radius: 0;
    animation: none;
    opacity: 1;
    transform: none;
    padding: 0;
    background-color: #34495e; /* Slightly lighter slate for mobile dropdown */
  }
  
  .dropdown-menu a {
    padding-left: 3rem;
  }
  
  .dropdown-toggle {
    justify-content: space-between;
  }
  
  .header-cta {
    margin-right: 1rem;
  }

  .cta-button {
    font-size: 0.9rem;
    padding: 0.5rem 1rem;
  }
}

@media (max-width: 576px) {
  .header-cta {
    display: none;
  }
}
</style>