<template>
    <footer class="footer">
      <!-- Main Footer -->
      <div class="footer-main">
        <div class="container">
          <div class="footer-grid">
            <!-- Company Info -->
            <div class="footer-col company-info">
              <div class="footer-logo">
                <img src="/assets/logos/lenergy-logo.svg" alt="Lenergy" height="40" />
              </div>
              <p>Your trusted partner for industrial fluid handling solutions. Providing top-quality hoses and fittings for industries worldwide.</p>
              <div class="social-links">
                <a href="#" class="social-icon" aria-label="LinkedIn">
                  <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"></path>
                    <rect x="2" y="9" width="4" height="12"></rect>
                    <circle cx="4" cy="4" r="2"></circle>
                  </svg>
                </a>
                <a href="#" class="social-icon" aria-label="Facebook">
                  <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <path d="M18 2h-3a5 5 0 0 0-5 5v3H7v4h3v8h4v-8h3l1-4h-4V7a1 1 0 0 1 1-1h3z"></path>
                  </svg>
                </a>
                <a href="#" class="social-icon" aria-label="Twitter">
                  <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <path d="M23 3a10.9 10.9 0 0 1-3.14 1.53 4.48 4.48 0 0 0-7.86 3v1A10.66 10.66 0 0 1 3 4s-4 9 5 13a11.64 11.64 0 0 1-7 2c9 5 20 0 20-11.5a4.5 4.5 0 0 0-.08-.83A7.72 7.72 0 0 0 23 3z"></path>
                  </svg>
                </a>
              </div>
            </div>
            
            <!-- Quick Links -->
            <div class="footer-col">
              <h3>Quick Links</h3>
              <ul class="footer-links">
                <li><router-link to="/">Home</router-link></li>
                <li><router-link to="/products">Products</router-link></li>
                <li><router-link to="/about">About Us</router-link></li>
                <li><router-link to="/contact">Contact</router-link></li>
              </ul>
            </div>
            
            <!-- Products -->
            <div class="footer-col">
              <h3>Products</h3>
              <ul class="footer-links">
                <li><router-link to="/products/industrial">Industrial Hoses</router-link></li>
                <li><router-link to="/products/oil-and-gas">Oil & Gas Hoses</router-link></li>
                <li><router-link to="/products/food-beverage">Food & Beverage Hoses</router-link></li>
                <li><router-link to="/products/chemical">Chemical Hoses</router-link></li>
                <li><router-link to="/products/fittings">Fittings & Couplings</router-link></li>
              </ul>
            </div>
            
            <!-- Contact Info -->
            <div class="footer-col">
              <h3>Contact Us</h3>
              <ul class="contact-info">
                <li>
                  <span class="icon">
                    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                      <path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"></path>
                      <circle cx="12" cy="10" r="3"></circle>
                    </svg>
                  </span>
                  <span>1234 Industrial Avenue<br>City, State 12345</span>
                </li>
                <li>
                  <span class="icon">
                    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                      <path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"></path>
                    </svg>
                  </span>
                  <span>+1 (123) 456-7890</span>
                </li>
                <li>
                  <span class="icon">
                    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                      <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"></path>
                      <polyline points="22,6 12,13 2,6"></polyline>
                    </svg>
                  </span>
                  <span>info@lenergy.com</span>
                </li>
              </ul>
            </div>
          </div>
        </div>
      </div>
      
      <!-- Footer Bottom -->
      <div class="footer-bottom">
        <div class="container">
          <div class="footer-bottom-content">
            <p>&copy; {{ currentYear }} Lenergy. All rights reserved.</p>
            <div class="footer-bottom-links">
              <a href="#">Privacy Policy</a>
              <a href="#">Terms of Service</a>
              <a href="#">Sitemap</a>
            </div>
          </div>
        </div>
      </div>
    </footer>
  </template>
  
  <script setup>
  import { computed } from 'vue';
  
  // Get current year for copyright
  const currentYear = computed(() => new Date().getFullYear());
  </script>
  
  <style scoped>
  .footer {
    background-color: #2c3e50;
    color: #ecf0f1;
    position: relative;
    z-index: 1;
  }
  
  .container {
    max-width: 1200px;
    width: 100%;
    margin: 0 auto;
    padding: 0 1rem;
  }
  
  /* Main Footer */
  .footer-main {
    padding: 4rem 0 3rem;
  }
  
  .footer-grid {
    display: grid;
    grid-template-columns: 2fr 1fr 1fr 1fr;
    gap: 2.5rem;
  }
  
  .footer-col h3 {
    color: white;
    font-size: 1.2rem;
    margin-bottom: 1.5rem;
    position: relative;
    padding-bottom: 0.8rem;
  }
  
  .footer-col h3::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 0;
    width: 50px;
    height: 2px;
    background-color: #e74c3c;
  }
  
  /* Company Info */
  .company-info p {
    margin: 1.2rem 0;
    line-height: 1.6;
    color: #bdc3c7;
  }
  
  .footer-logo {
    margin-bottom: 1rem;
  }
  
  .social-links {
    display: flex;
    gap: 1rem;
    margin-top: 1.5rem;
  }
  
  .social-icon {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 36px;
    height: 36px;
    border-radius: 50%;
    background-color: rgba(255, 255, 255, 0.1);
    color: white;
    transition: all 0.3s ease;
  }
  
  .social-icon:hover {
    background-color: #e74c3c;
    transform: translateY(-3px);
  }
  
  /* Footer Links */
  .footer-links {
    list-style: none;
    padding: 0;
  }
  
  .footer-links li {
    margin-bottom: 0.8rem;
  }
  
  .footer-links a {
    color: #bdc3c7;
    text-decoration: none;
    transition: color 0.3s ease;
    position: relative;
    padding-left: 15px;
  }
  
  .footer-links a::before {
    content: '›';
    position: absolute;
    left: 0;
    color: #e74c3c;
    font-size: 1.2rem;
    line-height: 1;
  }
  
  .footer-links a:hover {
    color: white;
    padding-left: 18px;
  }
  
  /* Contact Info */
  .contact-info {
    list-style: none;
    padding: 0;
  }
  
  .contact-info li {
    display: flex;
    margin-bottom: 1rem;
    color: #bdc3c7;
  }
  
  .contact-info .icon {
    margin-right: 10px;
    color: #e74c3c;
    display: flex;
    align-items: flex-start;
    padding-top: 3px;
  }
  
  /* Footer Bottom */
  .footer-bottom {
    background-color: #1a2530;
    padding: 1.5rem 0;
    font-size: 0.9rem;
  }
  
  .footer-bottom-content {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  
  .footer-bottom-links {
    display: flex;
    gap: 1.5rem;
  }
  
  .footer-bottom-links a {
    color: #bdc3c7;
    text-decoration: none;
    transition: color 0.3s ease;
  }
  
  .footer-bottom-links a:hover {
    color: white;
  }
  
  /* Responsive Adjustments */
  @media (max-width: 992px) {
    .footer-grid {
      grid-template-columns: 1fr 1fr 1fr;
    }
    
    .company-info {
      grid-column: span 3;
      margin-bottom: 1rem;
    }
  }
  
  @media (max-width: 768px) {
    .footer-main {
      padding: 3rem 0 2rem;
    }
    
    .footer-grid {
      grid-template-columns: 1fr 1fr;
      gap: 2rem;
    }
    
    .company-info {
      grid-column: span 2;
    }
    
    .footer-bottom-content {
      flex-direction: column;
      text-align: center;
      gap: 1rem;
    }
  }
  
  @media (max-width: 576px) {
    .footer-grid {
      grid-template-columns: 1fr;
    }
    
    .company-info {
      grid-column: span 1;
    }
  }
  </style>