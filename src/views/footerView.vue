<template>
  <footer
    class="footer"
    role="contentinfo"
    itemscope
    itemtype="http://schema.org/WPFooter"
  >
    <div class="footer-content">
      <div
        class="footer-left"
        itemscope
        itemtype="http://schema.org/Organization"
      >
        <img
          src="../assets/logo-swiss.png"
          alt="Logo"
          itemprop="logo"
          class="u-logo logo"
        />
        <p class="footer-name">Swiss Lake Capital © 2024</p>
      </div>

      <div class="footer-center">
        <div class="contact-info">
          <i class="fa fa-map-marker" aria-hidden="true"></i>
          <span>
            <strong>Address:</strong>
            <span itemprop="streetAddress" class="p-street-address"
              >Ajman Free Zone, Office - C1 - 1F - SF0410</span
            >, <span itemprop="addressLocality" class="p-locality">Ajman</span>,
            <span itemprop="addressRegion" class="p-region">UAE</span>
          </span>
        </div>

        <div class="contact-info">
          <i class="fa fa-phone" aria-hidden="true"></i>
          <span itemprop="telephone" class="p-tel">Phone: +20 1065840930</span>
        </div>

        <div class="contact-info">
          <i class="fa fa-envelope" aria-hidden="true"></i>
          <span>
            <a
              href="mailto:zeyadabdelaziz@swisslakecapital.com"
              itemprop="email"
              class="u-email"
              >Email: zeyadabdelaziz@swisslakecapital.com</a
            >
          </span>
        </div>
      </div>

      <div class="footer-right">
        <div class="footer-socials">
          <a
            href="#"
            rel="me"
            aria-label="Facebook"
            itemprop="sameAs"
            class="u-url"
            ><i class="fa-brands fa-facebook"></i
          ></a>
          <a
            href="#"
            rel="me"
            aria-label="Twitter"
            itemprop="sameAs"
            class="u-url"
            ><i class="fa-brands fa-x-twitter"></i
          ></a>
          <a
            href="#"
            rel="me"
            aria-label="LinkedIn"
            itemprop="sameAs"
            class="u-url"
            ><i class="fa-brands fa-linkedin"></i
          ></a>
          <a
            href="#"
            rel="me"
            aria-label="GitHub"
            itemprop="sameAs"
            class="u-url"
            ><i class="fa-brands fa-github"></i
          ></a>
        </div>
        <div class="footer-partner">
          <span></span>
          <img
            src="https://greenmarmot.com/images/Logo/LOGO_Green.png"
            alt="Green Marmot"
            class="partner-logo"
          />
          <p>Green marmot GmbH</p>
        </div>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  background: #0d1117;
  box-shadow: 0 1px 1px 0 rgba(0, 0, 0, 0.12);
  width: 100%;
  text-align: center; /* Centered text for better mobile experience */
  font: bold 16px sans-serif;
  padding: 20px; /* Adjusted padding */
  color: #fff !important;
}

.footer-content {
  display: flex;
  flex-direction: column; /* Stack all sections vertically */
  align-items: center; /* Center items */
}

.footer-left {
  margin-bottom: 15px; /* Space below logo */
}

.footer .footer-name {
  color: teal;
  font-size: 14px;
  font-weight: normal;
  margin: 5px 0; /* Adjusted margin */
}

/* Footer center */
.footer-center {
  margin-bottom: 15px; /* Space below center section */
}

.contact-info {
  display: flex;
  align-items: center; /* Align items vertically */
  justify-content: center; /* Center the content */
  margin: 5px 0; /* Space between contact items */
}

.contact-info i {
  margin-right: 8px; /* Space between icon and text */
}

/* Footer right */
.footer-right {
  margin-top: 15px; /* Space above right section */
}

.footer-socials {
  margin-bottom: 10px; /* Space below social icons */
}

.footer-socials a {
  display: inline-block;
  font-size: 30px;
  color: #ffffff;
  margin-right: 10px; /* Space between social icons */
}

.footer-partner {
  margin-bottom: 70px;
  text-align: center; /* Center align partner logo */
}
.footer .u-email {
  color: inherit; /* Inherit the color from the parent element */
  text-decoration: none; /* Remove underline */
}

.footer .partner-logo {
  max-width: 100px;
  margin-top: 5px; /* Space above logo */
}

.footer .logo {
  max-width: 300px; /* Adjusted logo size for better fit */
  height: auto;
}

@media (min-width: 800px) {
  .footer-content {
    flex-direction: row; /* Align items in a row for larger screens */
    justify-content: space-between; /* Space between items */
  }

  .footer-left,
  .footer-center,
  .footer-right {
    flex: 1; /* Allow sections to grow equally */
    text-align: left; /* Align text to the left on larger screens */
  }

  .footer-center {
    text-align: center; /* Center text in the footer center section on larger screens */
  }
}
</style>
