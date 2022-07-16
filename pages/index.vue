<template>
  <div id="main-section" class="py-4">
    <div class="d-flex justify-content-center flex-column container">
      <img src="@/assets/invissio-logo-default.png" class="mx-auto d-block mb-5" width="180px" />
      <p id="topmost-line" class="fw-bold text-center mb-3 letter-spacing-3">
        WEBSITE COMING SOON
      </p>
      <p id="title" class="display-5 text-center fw-lighter">
        Growth through <span class="blue-text">Innovation</span>  
      </p>
      <p id="description" class="text-center text-secondary fw-lighter fs-6 letter-spacing-1">
        <span class="fw-bold">Invissio</span> (<span class="fst-italic">formerly <span class="fw-bold">Intelliemed</span></span>) is a SaaS and IT solutions company that specializes in providing informatics software for educational institutions.
      </p>
      <LinkButton id="hyperlink-button" class="text-center mt-5 mb-4 position-relative" :icon="'bi-box-arrow-up-right'" :primaryText="'Visit Intelliemed Website'" :isPrimary="false" :nuxtLink="'https://intelliemed.com/'" />
    </div>
    <img id="main-section-primary-image" class="img-fluid user-select-none pe-none" src="@/assets/main-section-minified.png" />
  </div>
</template>

<script>
export default {
    name: "IndexPage",
}
</script>

<style scoped>
#topmost-line {
  font-size: 0.75rem;
}

#hyperlink-button {
  z-index: 999;
}

#main-section-primary-image {
  margin-top: -5vw;
}

.letter-spacing-3 {
  letter-spacing: 3px;
}

.blue-text {
  color: rgb(47, 123, 223) !important;
  font-weight: 400;
}

@media only screen and (max-width: 790px) {
  #main-section-primary-image {
    margin-top: 0vw;
  }
}

@media only screen and (max-width: 576px) {
  #topmost-line {
    font-size: 0.60rem;
  }
  #description {
    font-size: 0.9rem !important;
    letter-spacing: 0;
  }

  #main-section-primary-image {
    margin-top: 10px;
  }
}

@media only screen and (max-width: 480px) {
  #hyperlink-button {
    margin-top: 1.5rem !important;
  }
  
  #title {
    font-size: 1.8rem;
  }
  #description {
    font-size: 0.75rem !important;
    letter-spacing: 0;
  }
  #main-section-primary-image {
    margin-top: 20px;
  }
}
</style>
