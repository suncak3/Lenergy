<template>
  <div class="home">
    <!-- Hero Section -->
    <section class="hero">
      <div class="container">
        <div class="hero-content">
          <h1>Industrial Fluid Handling Solutions</h1>
          <p>Premium quality hoses and fittings for demanding industrial applications</p>
          <div class="hero-buttons">
            <router-link to="/products" class="btn btn-primary">Explore Products</router-link>
            <router-link to="/contact" class="btn btn-secondary">Contact Us</router-link>
          </div>
        </div>
      </div>
    </section>

    <!-- Key Benefits Section -->
    <section class="key-benefits">
      <div class="container">
        <div class="benefits-grid">
          <div class="benefit-card">
            <div class="benefit-icon">
              <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                <path d="M22 11.08V12a10 10 0 1 1-5.93-9.14"></path>
                <polyline points="22 4 12 14.01 9 11.01"></polyline>
              </svg>
            </div>
            <h3>Premium Quality</h3>
            <p>Our products meet the highest industry standards, ensuring durability and reliability.</p>
          </div>
          
          <div class="benefit-card">
            <div class="benefit-icon">
              <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                <circle cx="12" cy="12" r="10"></circle>
                <line x1="12" y1="16" x2="12" y2="12"></line>
                <line x1="12" y1="8" x2="12.01" y2="8"></line>
              </svg>
            </div>
            <h3>Expert Support</h3>
            <p>Our technical specialists provide guidance to help you select the right solutions.</p>
          </div>
          
          <div class="benefit-card">
            <div class="benefit-icon">
              <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                <path d="M21 16V8a2 2 0 0 0-1-1.73l-7-4a2 2 0 0 0-2 0l-7 4A2 2 0 0 0 3 8v8a2 2 0 0 0 1 1.73l7 4a2 2 0 0 0 2 0l7-4A2 2 0 0 0 21 16z"></path>
                <polyline points="7.5 4.21 12 6.81 16.5 4.21"></polyline>
                <polyline points="7.5 19.79 7.5 14.6 3 12"></polyline>
                <polyline points="21 12 16.5 14.6 16.5 19.79"></polyline>
                <polyline points="3.27 6.96 12 12.01 20.73 6.96"></polyline>
                <line x1="12" y1="22.08" x2="12" y2="12"></line>
              </svg>
            </div>
            <h3>Custom Solutions</h3>
            <p>Tailored options designed to meet the unique requirements of your application.</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Product Categories Section -->
    <section class="product-categories">
      <div class="container">
        <h2>Our Product Range</h2>
        <div class="categories-grid">
          <div class="category-card">
            <div class="category-image industrial"></div>
            <div class="category-content">
              <h3>Industrial Hoses</h3>
              <p>Reliable hoses for various industrial applications including material handling, ventilation, and general purpose use.</p>
              <router-link to="/products/industrial" class="category-link">View Products</router-link>
            </div>
          </div>
          
          <div class="category-card">
            <div class="category-image oil-gas"></div>
            <div class="category-content">
              <h3>Oil & Gas Hoses</h3>
              <p>Specialized hoses designed for the demanding conditions of the oil and gas industry.</p>
              <router-link to="/products/oil-and-gas" class="category-link">View Products</router-link>
            </div>
          </div>
          
          <div class="category-card">
            <div class="category-image chemical"></div>
            <div class="category-content">
              <h3>Chemical Hoses</h3>
              <p>Corrosion-resistant hoses for safe transfer of a wide range of chemicals and aggressive media.</p>
              <router-link to="/products/chemical" class="category-link">View Products</router-link>
            </div>
          </div>
          
          <div class="category-card">
            <div class="category-image fittings"></div>
            <div class="category-content">
              <h3>Fittings & Couplings</h3>
              <p>Comprehensive range of fittings and couplings to ensure secure connections for all applications.</p>
              <router-link to="/products/fittings" class="category-link">View Products</router-link>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Call to Action Section -->
    <section class="cta-section">
      <div class="container">
        <div class="cta-content">
          <h2>Ready to Find Your Perfect Fluid Handling Solution?</h2>
          <p>Contact our team today to discuss your specific requirements and get expert recommendations.</p>
          <router-link to="/contact" class="btn btn-primary">Get in Touch</router-link>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
// No additional functionality needed for this component
</script>

<style scoped>
/* Hero Section */
.hero {
  background-color: #2c3e50;
  color: white;
  padding: 5rem 0;
  position: relative;
  background-image: linear-gradient(rgba(44, 62, 80, 0.85), rgba(44, 62, 80, 0.9)), url('/assets/images/hero-bg.jpg');
  background-size: cover;
  background-position: center;
}

.container {
  max-width: 1200px;
  width: 100%;
  margin: 0 auto;
  padding: 0 1rem;
}

.hero-content {
  max-width: 650px;
}

.hero h1 {
  font-size: 2.8rem;
  margin-bottom: 1rem;
  line-height: 1.2;
}

.hero p {
  font-size: 1.2rem;
  margin-bottom: 2rem;
  opacity: 0.9;
}

.hero-buttons {
  display: flex;
  gap: 1rem;
}

.btn {
  display: inline-block;
  padding: 0.8rem 1.6rem;
  border-radius: 4px;
  text-decoration: none;
  font-weight: 500;
  transition: all 0.3s ease;
}

.btn-primary {
  background-color: #e74c3c;
  color: white;
  border: 2px solid #e74c3c;
}

.btn-primary:hover {
  background-color: #c0392b;
  border-color: #c0392b;
  transform: translateY(-2px);
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.btn-secondary {
  background-color: transparent;
  border: 2px solid white;
  color: white;
}

.btn-secondary:hover {
  background-color: rgba(255, 255, 255, 0.1);
  transform: translateY(-2px);
}

/* Key Benefits Section */
.key-benefits {
  padding: 5rem 0;
  background-color: #f7f9fa;
}

.benefits-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.benefit-card {
  background-color: white;
  padding: 2rem;
  border-radius: 8px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.benefit-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
}

.benefit-icon {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 60px;
  height: 60px;
  border-radius: 50%;
  background-color: rgba(231, 76, 60, 0.1);
  color: #e74c3c;
  margin-bottom: 1.5rem;
}

.benefit-card h3 {
  font-size: 1.4rem;
  margin-bottom: 1rem;
  color: #2c3e50;
}

/* Product Categories Section */
.product-categories {
  padding: 5rem 0;
}

.product-categories h2 {
  text-align: center;
  font-size: 2.2rem;
  margin-bottom: 3rem;
  color: #2c3e50;
}

.categories-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 2rem;
}

.category-card {
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
  background-color: white;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.category-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
}

.category-image {
  height: 200px;
  background-size: cover;
  background-position: center;
}

.category-image.industrial {
  background-image: url('/assets/images/industrial-hoses.jpg');
  background-color: #34495e; /* Fallback */
}

.category-image.oil-gas {
  background-image: url('/assets/images/oil-gas-hoses.jpg');
  background-color: #34495e; /* Fallback */
}

.category-image.chemical {
  background-image: url('/assets/images/chemical-hoses.jpg');
  background-color: #34495e; /* Fallback */
}

.category-image.fittings {
  background-image: url('/assets/images/fittings.jpg');
  background-color: #34495e; /* Fallback */
}

.category-content {
  padding: 1.5rem;
}

.category-content h3 {
  font-size: 1.3rem;
  margin-bottom: 0.8rem;
  color: #2c3e50;
}

.category-link {
  display: inline-block;
  margin-top: 1rem;
  color: #e74c3c;
  font-weight: 500;
  text-decoration: none;
  position: relative;
}

.category-link::after {
  content: '';
  position: absolute;
  bottom: -2px;
  left: 0;
  width: 0;
  height: 2px;
  background-color: #e74c3c;
  transition: width 0.3s ease;
}

.category-link:hover::after {
  width: 100%;
}

/* Call to Action Section */
.cta-section {
  padding: 5rem 0;
  background-color: #2c3e50;
  color: white;
}

.cta-content {
  text-align: center;
  max-width: 800px;
  margin: 0 auto;
}

.cta-content h2 {
  font-size: 2.2rem;
  margin-bottom: 1.2rem;
}

.cta-content p {
  margin-bottom: 2rem;
  font-size: 1.1rem;
  opacity: 0.9;
}

/* Responsive Adjustments */
@media (max-width: 768px) {
  .hero h1 {
    font-size: 2.2rem;
  }
  
  .hero-buttons {
    flex-direction: column;
  }
  
  .key-benefits {
    padding: 3rem 0;
  }
  
  .product-categories {
    padding: 3rem 0;
  }
  
  .product-categories h2 {
    font-size: 1.8rem;
    margin-bottom: 2rem;
  }
  
  .cta-section {
    padding: 3rem 0;
  }
  
  .cta-content h2 {
    font-size: 1.8rem;
  }
}
</style>