<template>
  <div class="home">
    <!-- Updated Hero Section - Centered with animated elements -->
    <section class="hero">
      <div class="hero-background">
        <div class="animated-line"></div>
        <div class="animated-line"></div>
        <div class="animated-line"></div>
      </div>
      <div class="container">
        <div class="hero-content">
          <div class="hero-logo">
            <img src="/assets/logos/lenergy-logo.svg" alt="Lenergy" height="60" />
          </div>
          <h1>Industrial Fluid Handling Solutions</h1>
          <p>Precision-engineered hoses and fittings for your most demanding applications</p>
          <div class="hero-actions">
            <router-link to="/products" class="btn-primary">Explore Products</router-link>
            <router-link to="/contact" class="btn-outline">Get in Touch</router-link>
          </div>
          <div class="scroll-indicator">
            <span>Scroll to discover</span>
            <div class="scroll-arrow"></div>
          </div>
        </div>
      </div>
    </section>

    <!-- Benefits Section - Card Slider -->
    <section class="benefits">
      <h2>Why Choose Lenergy</h2>
      <div class="slider-container">
        <div class="slider-track" ref="sliderTrack">
          <div class="benefit-card" v-for="(benefit, index) in benefits" :key="index">
            <div class="benefit-icon" :style="{ backgroundColor: benefit.bgColor }">
              <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path :d="benefit.icon"></path>
              </svg>
            </div>
            <h3>{{ benefit.title }}</h3>
            <p>{{ benefit.description }}</p>
          </div>
        </div>
        <div class="slider-controls">
          <button @click="scrollSlider('left')" class="slider-arrow">←</button>
          <button @click="scrollSlider('right')" class="slider-arrow">→</button>
        </div>
      </div>
    </section>

    <!-- Products Grid with Accent Borders -->
    <section class="products">
      <h2>Our Products</h2>
      <div class="products-grid">
        <div class="product-category" v-for="(product, index) in products" :key="index">
          <div class="accent-border" :style="{ backgroundColor: product.accentColor }"></div>
          <h3>{{ product.title }}</h3>
          <p>{{ product.description }}</p>
          <router-link :to="product.link" class="view-link">Explore →</router-link>
        </div>
      </div>
    </section>

    <!-- Updated CTA Section - Overlapping elements with depth -->
    <section class="cta">
      <div class="cta-background">
        <div class="bg-shape shape1"></div>
        <div class="bg-shape shape2"></div>
        <div class="bg-shape shape3"></div>
      </div>
      <div class="container">
        <div class="cta-card">
          <div class="cta-content">
            <h2>Ready for Your Custom Solution?</h2>
            <p>Our engineering team is ready to help you find the perfect fluid handling solution for your specific requirements.</p>
            <router-link to="/contact" class="btn-primary pulse">Contact Us Today</router-link>
          </div>
          <div class="cta-image-container">
            <div class="cta-image-overlay"></div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
import { ref } from 'vue';

// Benefits data
const benefits = [
  {
    title: 'Quality Assurance',
    description: 'All products undergo rigorous testing to ensure long-term reliability.',
    icon: 'M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z',
    bgColor: '#e74c3c'
  },
  {
    title: 'Engineering Expertise',
    description: 'Our team brings decades of experience in fluid handling technology.',
    icon: 'M19.4 15a1.65 1.65 0 0 0 .33 1.82l.06.06a2 2 0 0 1 0 2.83 2 2 0 0 1-2.83 0l-.06-.06a1.65 1.65 0 0 0-1.82-.33 1.65 1.65 0 0 0-1 1.51V21a2 2 0 0 1-2 2 2 2 0 0 1-2-2v-.09A1.65 1.65 0 0 0 9 19.4a1.65 1.65 0 0 0-1.82.33l-.06.06a2 2 0 0 1-2.83 0 2 2 0 0 1 0-2.83l.06-.06a1.65 1.65 0 0 0 .33-1.82 1.65 1.65 0 0 0-1.51-1H3a2 2 0 0 1-2-2 2 2 0 0 1 2-2h.09A1.65 1.65 0 0 0 4.6 9a1.65 1.65 0 0 0-.33-1.82l-.06-.06a2 2 0 0 1 0-2.83 2 2 0 0 1 2.83 0l.06.06a1.65 1.65 0 0 0 1.82.33H9a1.65 1.65 0 0 0 1-1.51V3a2 2 0 0 1 2-2 2 2 0 0 1 2 2v.09a1.65 1.65 0 0 0 1 1.51 1.65 1.65 0 0 0 1.82-.33l.06-.06a2 2 0 0 1 2.83 0 2 2 0 0 1 0 2.83l-.06.06a1.65 1.65 0 0 0-.33 1.82V9a1.65 1.65 0 0 0 1.51 1H21a2 2 0 0 1 2 2 2 2 0 0 1-2 2h-.09a1.65 1.65 0 0 0-1.51 1z',
    bgColor: '#3498db'
  },
  {
    title: 'Custom Solutions',
    description: 'We develop tailored products to meet your specific requirements.',
    icon: 'M11 4a2 2 0 114 0v1a1 1 0 001 1h3a1 1 0 011 1v3a1 1 0 01-1 1h-1a2 2 0 100 4h1a1 1 0 011 1v3a1 1 0 01-1 1h-3a1 1 0 01-1-1v-1a2 2 0 10-4 0v1a1 1 0 01-1 1H7a1 1 0 01-1-1v-3a1 1 0 00-1-1H4a2 2 0 110-4h1a1 1 0 001-1V7a1 1 0 011-1h3a1 1 0 001-1V4z',
    bgColor: '#2ecc71'
  },
  {
    title: 'Global Support',
    description: 'Our network provides assistance wherever your operations are located.',
    icon: 'M21 12a9 9 0 01-9 9m9-9a9 9 0 00-9-9m9 9H3m9 9a9 9 0 01-9-9m9 9c1.657 0 3-4.03 3-9s-1.343-9-3-9m0 18c-1.657 0-3-4.03-3-9s1.343-9 3-9m-9 9a9 9 0 019-9',
    bgColor: '#f39c12'
  },
  {
    title: 'Fast Delivery',
    description: 'Optimized logistics ensure your products arrive when you need them.',
    icon: 'M13 10V3L4 14h7v7l9-11h-7z',
    bgColor: '#9b59b6'
  }
];

// Products data
const products = [
  {
    title: 'Industrial Hoses',
    description: 'Durable solutions for manufacturing, construction, and general industry applications.',
    link: '/products/industrial',
    accentColor: '#3498db'
  },
  {
    title: 'Oil & Gas Hoses',
    description: 'Specialized equipment for the demanding conditions of petroleum industry.',
    link: '/products/oil-and-gas',
    accentColor: '#e67e22'
  },
  {
    title: 'Chemical Hoses',
    description: 'Corrosion-resistant options for safe transfer of chemicals and aggressive media.',
    link: '/products/chemical',
    accentColor: '#9b59b6'
  },
  {
    title: 'Fittings & Couplings',
    description: 'Precision-engineered connection systems for secure and reliable fluid transfer.',
    link: '/products/fittings',
    accentColor: '#2ecc71'
  }
];

// Slider functionality
const sliderTrack = ref(null);

const scrollSlider = (direction) => {
  if (!sliderTrack.value) return;
  
  const cardWidth = 300; // Width of each card + margins
  const currentScroll = sliderTrack.value.scrollLeft;
  
  if (direction === 'left') {
    sliderTrack.value.scrollTo({
      left: currentScroll - cardWidth,
      behavior: 'smooth'
    });
  } else {
    sliderTrack.value.scrollTo({
      left: currentScroll + cardWidth,
      behavior: 'smooth'
    });
  }
};
</script>

<style scoped>
/* Base Styles */

.home {
  color: #2c3e50;
}

section {
  padding: 80px 0;
}

h2 {
  font-size: 2.2rem;
  text-align: center;
  margin-bottom: 3rem;
  position: relative;
}

h2::after {
  content: '';
  position: absolute;
  bottom: -10px;
  left: 50%;
  transform: translateX(-50%);
  width: 60px;
  height: 3px;
  background-color: #e74c3c;
}

/* Updated Hero Section */
.hero {
  position: relative;
  min-height: 90vh;
  display: flex;
  align-items: center;
  overflow: hidden;
  background-color: #f8f9fa;
}

.hero-background {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  overflow: hidden;
}

.animated-line {
  position: absolute;
  height: 3px;
  background-color: rgba(231, 76, 60, 0.1);
  width: 100%;
  transform-origin: left;
}

.animated-line:nth-child(1) {
  top: 20%;
  animation: lineFlow 15s linear infinite;
}

.animated-line:nth-child(2) {
  top: 50%;
  animation: lineFlow 20s linear infinite;
  animation-delay: -5s;
}

.animated-line:nth-child(3) {
  top: 80%;
  animation: lineFlow 18s linear infinite;
  animation-delay: -10s;
}

@keyframes lineFlow {
  0% {
    transform: translateX(-100%) scaleX(1);
  }
  50% {
    transform: translateX(0) scaleX(1.5);
  }
  100% {
    transform: translateX(100%) scaleX(1);
  }
}

.container {
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
  position: relative;
  z-index: 1;
}

.hero-content {
  text-align: center;
  max-width: 800px;
  margin: 0 auto;
  padding: 40px 0;
}

.hero-logo {
  margin-bottom: 30px;
}

.hero-logo img {
  filter: drop-shadow(0 4px 6px rgba(0, 0, 0, 0.1));
}

.hero h1 {
  font-size: 3.5rem;
  line-height: 1.2;
  margin-bottom: 1.5rem;
  font-weight: 700;
  color: #2c3e50;
  position: relative;
}

.hero h1::after {
  content: '';
  position: absolute;
  bottom: -15px;
  left: 50%;
  transform: translateX(-50%);
  width: 80px;
  height: 3px;
  background-color: #e74c3c;
}

.hero p {
  font-size: 1.3rem;
  margin-bottom: 2.5rem;
  max-width: 600px;
  line-height: 1.6;
  margin-left: auto;
  margin-right: auto;
  color: #7f8c8d;
}

.hero-actions {
  display: flex;
  gap: 20px;
  justify-content: center;
  margin-bottom: 60px;
}

.btn-primary {
  display: inline-block;
  background-color: #e74c3c;
  color: white;
  padding: 12px 24px;
  border-radius: 4px;
  text-decoration: none;
  font-weight: 500;
  transition: all 0.3s ease;
}

.btn-primary:hover {
  background-color: #c0392b;
  transform: translateY(-2px);
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.btn-outline {
  display: inline-block;
  border: 2px solid #2c3e50;
  color: #2c3e50;
  padding: 12px 24px;
  border-radius: 4px;
  text-decoration: none;
  font-weight: 500;
  transition: all 0.3s ease;
}

.btn-outline:hover {
  background-color: #2c3e50;
  color: white;
  transform: translateY(-2px);
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.scroll-indicator {
  position: absolute;
  bottom: 40px;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  flex-direction: column;
  align-items: center;
  color: #95a5a6;
  font-size: 0.9rem;
}

.scroll-arrow {
  margin-top: 8px;
  width: 20px;
  height: 30px;
  border: 2px solid #95a5a6;
  border-radius: 10px;
  position: relative;
}

.scroll-arrow::before {
  content: '';
  position: absolute;
  top: 6px;
  left: 50%;
  transform: translateX(-50%);
  width: 4px;
  height: 4px;
  background-color: #95a5a6;
  border-radius: 50%;
  animation: scrollDown 2s infinite;
}

@keyframes scrollDown {
  0% {
    opacity: 1;
    transform: translateX(-50%) translateY(0);
  }
  100% {
    opacity: 0;
    transform: translateX(-50%) translateY(12px);
  }
}

/* Benefits Section - Card Slider */
.benefits {
  background-color: #f0f4f8;
  padding: 80px 20px;
}

.slider-container {
  position: relative;
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px 0;
}

.slider-track {
  display: flex;
  gap: 20px;
  overflow-x: auto;
  scroll-behavior: smooth;
  padding: 20px 0;
  scrollbar-width: none; /* Firefox */
}

.slider-track::-webkit-scrollbar {
  display: none; /* Chrome, Safari, Opera */
}

.benefit-card {
  flex: 0 0 280px;
  padding: 30px;
  background: white;
  border-radius: 8px;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.benefit-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
}

.benefit-icon {
  width: 60px;
  height: 60px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 20px;
  color: white;
}

.benefit-card h3 {
  margin-bottom: 15px;
  font-size: 1.2rem;
}

.benefit-card p {
  color: #7f8c8d;
  line-height: 1.6;
}

.slider-controls {
  display: flex;
  justify-content: center;
  gap: 10px;
  margin-top: 30px;
}

.slider-arrow {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  border: none;
  background-color: #2c3e50;
  color: white;
  font-size: 18px;
  cursor: pointer;
  transition: all 0.3s ease;
}

.slider-arrow:hover {
  background-color: #e74c3c;
}

/* Products Grid with Accent Borders */
.products {
  background-color: #f8f9fa;
  padding: 80px 20px;
}

.products-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 30px;
  max-width: 1200px;
  margin: 0 auto;
}

.product-category {
  background-color: white;
  border-radius: 8px;
  overflow: hidden;
  position: relative;
  padding: 30px;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
  transition: transform 0.3s ease;
}

.product-category:hover {
  transform: translateY(-5px);
}

.accent-border {
  height: 6px;
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
}

.product-category h3 {
  margin-bottom: 15px;
  font-size: 1.4rem;
}

.product-category p {
  color: #7f8c8d;
  margin-bottom: 20px;
  line-height: 1.6;
}

.view-link {
  color: #e74c3c;
  text-decoration: none;
  font-weight: 500;
  transition: all 0.3s ease;
}

.view-link:hover {
  margin-left: 5px;
}

/* Updated CTA Section */
.cta {
  position: relative;
  padding: 100px 0;
  overflow: hidden;
  background-color: #2c3e50;
}

.cta-background {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
}

.bg-shape {
  position: absolute;
  border-radius: 50%;
  opacity: 0.1;
}

.shape1 {
  width: 400px;
  height: 400px;
  background-color: #e74c3c;
  top: -150px;
  left: -100px;
}

.shape2 {
  width: 300px;
  height: 300px;
  background-color: #3498db;
  bottom: -100px;
  right: -50px;
}

.shape3 {
  width: 200px;
  height: 200px;
  background-color: #f1c40f;
  top: 50%;
  right: 20%;
}

.cta-card {
  background-color: white;
  border-radius: 16px;
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.2);
  overflow: hidden;
  display: flex;
  position: relative;
  z-index: 2;
}

.cta-content {
  padding: 60px;
  flex: 3;
}

.cta-content h2 {
  text-align: left;
  margin-bottom: 20px;
  color: #2c3e50;
}

.cta-content h2::after {
  left: 0;
  transform: none;
}

.cta-content p {
  color: #7f8c8d;
  margin-bottom: 30px;
  line-height: 1.6;
}

.pulse {
  animation: pulse 2s infinite;
}

@keyframes pulse {
  0% {
    box-shadow: 0 0 0 0 rgba(231, 76, 60, 0.4);
  }
  70% {
    box-shadow: 0 0 0 10px rgba(231, 76, 60, 0);
  }
  100% {
    box-shadow: 0 0 0 0 rgba(231, 76, 60, 0);
  }
}

.cta-image-container {
  flex: 2;
  background-image: url('/assets/images/cta-image.jpg');
  background-size: cover;
  background-position: center;
  position: relative;
  min-height: 350px;
  background-color: #34495e; /* Fallback */
}

.cta-image-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(to right, white, rgba(255, 255, 255, 0.3));
}

/* Responsive Adjustments */
@media (max-width: 992px) {
  .hero h1 {
    font-size: 2.8rem;
  }
  
  .cta-card {
    flex-direction: column;
    margin: 0 20px; /* Add margin on smaller screens */
  }
  
  .cta-image-container {
    height: 250px;
    order: -1;
  }
  
  .cta-image-overlay {
    background: linear-gradient(to bottom, rgba(255, 255, 255, 0.3), white);
  }

  .cta-image-container {
    display: none;
  }
  
}

@media (max-width: 768px) {
  section {
    padding: 60px 0;
  }
  
  .hero h1 {
    font-size: 2.2rem;
  }
  
  .hero p {
    font-size: 1.1rem;
  }
  
  .hero-actions {
    flex-direction: column;
    max-width: 250px;
    margin-left: auto;
    margin-right: auto;
  }
  

  
  /* Ensure text remains visible on small screens */
  .cta-content h2 {
    font-size: 1.8rem;
  }
  
  .cta-content p {
    font-size: 1rem;
  }

  /* Hide the image container altogether */
  .cta-image-container {
    display: none;
  }
}

@media (max-width: 576px) {
  .hero-logo img {
    height: 50px;
  }
  
  .hero h1 {
    font-size: 1.8rem;
  }
  
  .scroll-indicator {
    display: none;
  }
  
  /* Fix for very small screens */
  .cta {
    padding: 30px 0;
  }
  
  .cta-card {
    margin: 0 15px;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.15);
  }
  
  .cta-content {
    padding: 25px 15px;
  }
  
  .cta-content h2 {
    font-size: 1.5rem;
  }
  
  /* Ensure the button is properly sized and aligned */
  .cta .btn-primary {
    display: block;
    text-align: center;
    padding: 12px 15px;
  }

  .cta-image-container {
    height: 20px; /* Make the image area even smaller */
  }

  .cta-image-container {
    display: none;
  }

}

/* Add this new breakpoint for extra small devices */
@media (max-width: 380px) {
  .cta-card {
    margin: 0 10px;
  }
  
  .cta-content {
    padding: 20px 15px;
  }
  
  .cta-content h2 {
    font-size: 1.3rem;
  }
  
  .cta-content p {
    font-size: 0.9rem;
    margin-bottom: 20px;
  }

  .cta-image-container {
    display: none;
  }
}
</style>