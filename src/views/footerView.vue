<template>
  <footer
    class="footer"
    role="contentinfo"
    itemscope
    itemtype="http://schema.org/WPFooter"
  >
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
      <div
        itemscope
        itemtype="http://schema.org/PostalAddress"
        class="p-address"
      >
        <i class="fa fa-map-marker" aria-hidden="true"></i>
        <p>
          Address:
          <span itemprop="streetAddress" class="p-street-address"
            >Ajman Free Zone, Office - C1 - 1F - SF0410</span
          >, <span itemprop="addressLocality" class="p-locality">Ajman</span>,
          <span itemprop="addressRegion" class="p-region">UAE</span>
        </p>
      </div>
      <div>
        <i class="fa fa-phone" aria-hidden="true"></i>
        <p itemprop="telephone" class="p-tel">Phone: +20 1065840930</p>
      </div>
      <div>
        <i class="fa fa-envelope" aria-hidden="true"></i>
        <p>
          <a
            href="mailto:zeyadabdelaziz@swisslakecapital.com"
            itemprop="email"
            class="u-email"
            >Email: zeyadabdelaziz@swisslakecapital.com</a
          >
        </p>
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
        <a href="#" rel="me" aria-label="GitHub" itemprop="sameAs" class="u-url"
          ><i class="fa-brands fa-github"></i
        ></a>
      </div>
      <div class="footer-partner">
        <span>Our Partner:</span>
        <img
          src="https://greenmarmot.com/images/Logo/LOGO_Green.png"
          alt="Green Marmot"
          class="partner-logo"
        />
      </div>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  background: #0d1117;
  box-shadow: 0 1px 1px 0 rgba(0, 0, 0, 0.12);
  box-sizing: border-box;
  width: 100%;
  text-align: left;
  font: bold 16px sans-serif;
  padding: 55px 50px;
  color: #fff !important;
}

.footer .footer-left,
.footer .footer-center,
.footer .footer-right {
  display: inline-block;
  vertical-align: top;
}

/* Footer left */
.footer .footer-left {
  width: 35%;
}

.footer .footer-name {
  color: teal;
  font-size: 14px;
  font-weight: normal;
  margin: 0;
}

/* Footer center */
.footer .footer-center {
  width: 40%;
}

.footer .footer-center i {
  background-color: #33383b;
  color: #ffffff;
  font-size: 25px;
  width: 38px;
  height: 38px;
  border-radius: 50%;
  text-align: center;
  line-height: 42px;
  margin: 10px 15px;
  vertical-align: middle;
}

.footer .footer-center p {
  display: inline-block;
  color: #ffffff;
  font-weight: 400;
  vertical-align: middle;
  margin: 0;
}

.footer .footer-center p a {
  color: teal;
  text-decoration: none;
}

/* Footer right */
.footer .footer-right {
  width: 20%;
}

.footer .footer-socials {
  margin-top: 15px;
}

.footer .footer-socials a {
  display: inline-block;
  font-size: 30px;
  cursor: pointer;
  color: #ffffff;
  text-align: center;
  line-height: 35px;
  margin-right: 10px;
  margin-bottom: 10px;
}

.footer .footer-partner {
  margin-top: 15px;
  text-align: center;
}

.footer .partner-logo {
  max-width: 100px;
  margin-top: 10px;
}

.footer .logo {
  max-width: 100px;
  height: auto;
  margin-bottom: 15px;
}

@media (max-width: 800px) {
  .footer {
    font: bold 14px sans-serif;
  }

  .footer .footer-left,
  .footer .footer-center,
  .footer .footer-right {
    display: block;
    width: 100%;
    margin-bottom: 30px;
    text-align: center;
  }

  .footer .footer-center i {
    margin-left: 0;
  }

  .footer .footer-partner {
    margin-top: 20px;
  }
}
</style>
