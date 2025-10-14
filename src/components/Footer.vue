<script>
export default {}
</script>

<template>
  <footer class="footer">
    <div class="footer-container">
      <!-- Location Section -->
      <div class="footer-section location">
        <h3>Our Location</h3>
        <div class="map">
          
          <iframe
            src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3988.8495638089354!2d37.0126!3d-1.1045!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x182f1184d2d1b7a7%3A0xfacdfd899345ae3a!2sKonza%20Technopolis!5e0!3m2!1sen!2ske!4v1700000000000!5m2!1sen!2ske"
            width="100%"
            height="180"
            style="border: 0; border-radius: 10px"
            allowfullscreen=""
            loading="lazy"
          ></iframe>
        </div>
      </div>

      <!-- Contact Section -->
      <div class="footer-section contact">
        <h3>Contact Us</h3>
        <p>Nairobi-Mombasa Road</p>
        <p>P.O BOX 30, Nairobi</p>
        <p>Email: <a href="mailto:info@precious.sc.ke">info@precious.sc.ke</a></p>
        <p>Phone: <a href="tel:+254784606060">+254 784 606060</a></p>
      </div>

      <!-- Social Media Section -->
      <div class="footer-section social-media">
        <h3>Follow Us</h3>
        <div class="social-links">
          <a href="#" aria-label="Facebook"><i class="fab fa-facebook-f"></i> Facebook</a>
          <a href="#" aria-label="Twitter"><i class="fab fa-twitter"></i> Twitter</a>
          <a href="#" aria-label="Instagram"><i class="fab fa-instagram"></i> Instagram</a>
          <a href="#" aria-label="LinkedIn"><i class="fab fa-linkedin-in"></i> LinkedIn</a>
        </div>
      </div>
    </div>

    <!-- Bottom Copyright -->
    <div class="footer-bottom">
      <p>
        &copy; 2025 Precious School | Developed by
        <a href="https://quantumripple.co.ke/" target="_blank">Quantum Ripple LTD</a>
      </p>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  background: rgb(125, 5, 5);
  color: #fff;
  padding: 60px 10% 30px;
  font-family: "Poppins", sans-serif;
  margin-top: 40px;
}

.footer-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  gap: 40px;
  margin-bottom: 40px;
}

.footer-section {
  flex: 1;
  min-width: 280px;
}

.footer-section h3 {
  font-size: 1.4rem;
  color: #ffb400;
  margin-bottom: 20px;
  border-left: 4px solid #ffb400;
  padding-left: 10px;
  text-transform: uppercase;
  letter-spacing: 1px;
}

.footer-section p {
  margin: 8px 0;
  font-size: 1rem;
  line-height: 1.5;
}

.footer-section a {
  color: #ccc;
  text-decoration: none;
  transition: color 0.3s ease;
}

.footer-section a:hover {
  color: #ffb400;
}

.social-links {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.social-links a {
  display: flex;
  align-items: center;
  gap: 10px;
}

.social-links i {
  width: 20px;
}

.footer-bottom {
  text-align: center;
  padding-top: 20px;
  border-top: 1px solid rgba(255, 255, 255, 0.1);
  font-size: 0.9rem;
}

.footer-bottom a {
  color: #ffb400;
  text-decoration: none;
}

.footer-bottom a:hover {
  text-decoration: underline;
}

@media (max-width: 768px) {
  .footer {
    padding: 40px 5% 20px;
  }

  .footer-container {
    flex-direction: column;
    gap: 30px;
  }

  .footer-section {
    min-width: 100%;
  }
}


/* Social Media Styling */
.social-links {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.social-links a i {
  margin-right: 8px;
}

.social-links a:hover {
  transform: translateX(5px);
  transition: all 0.3s ease;
}

/* Bottom Footer */
.footer-bottom {
  text-align: center;
  border-top: 1px solid #333;
  padding-top: 20px;
  font-size: 0.95rem;
  color: #bbb;

}

.footer-bottom a {
  color: #ffb400;
  text-decoration: none;
  font-weight: 500;
}

.footer-bottom a:hover {
  text-decoration: underline;
}


@media (max-width: 900px) {
  .footer-container {
    flex-direction: column;
    align-items: center;
  }

  .footer-section {
    text-align: center;
  }

  .footer-section h3 {
    border-left: none;
    border-bottom: 2px solid #ffb400;
    padding-left: 0;
    padding-bottom: 8px;
    display: inline-block;
  }
}
</style>
