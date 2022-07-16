<template>
<div>
  <a class="fw-bold nuxtLink" v-bind:style="styleObject" :href="nuxtLink">
    <span v-if="primaryText !== ''" class="me-2">
      {{ primaryText }}
    </span>
    <i v-if="icon !== ''" :class="`bi ${icon}`"></i>
  </a>
</div>
<!-- div 
  NuxtLink.fw-bold.nuxtLink(v-bind:style="styleObject" :to="nuxtLink")
    span.me-2(v-if="primaryText !== ''") {{ primaryText }}
    i(v-if="icon !== ''" :class="`bi ${icon}`") -->
</template>

<script>
export default {
  name: "LinkButton",
  props: {
    primaryText: {
      type: String,
      default: ''
    },
    isPrimary: {
      type: Boolean,
      default: true,
    },
    backgroundColor: {
      type: String,
      default: "blue"
    },
    nuxtLink: {
      type: String,
      required: true
    },
    icon: {
      type: String,
      default: ''
    },
    isLinkStyle: {
      type: Boolean,
      default: false,
    }
  },
  computed: {
    styleObject() {
      const backgroundColor = this.backgroundColor === 'blue' ? '#0e60ad' : this.backgroundColor
      const style = {
        backgroundColor: this.isPrimary ? backgroundColor : 'transparent',
        color: '#ffffff'
      }

      if (!this.isPrimary) {
        style.color = backgroundColor
        style.border = `1px solid ${backgroundColor}`
      }

      if (this.isLinkStyle) {
        style.color = '#2c3e50'
        style.backgroundColor = 'transparent'
        style.border = ''
        style.padding = 0
      }

      if (this.backgroundColor === '#ffffff') {
        style.color = '#2c3e50'
      }

      if (this.primaryText === '') {
        style.fontSize = '30px'
        style.color = '#0e60ad'
        style.padding = '0 !important';
      }

      return style
    }
  }
}
</script>

<style scoped>
  .nuxtLink {
    z-index: 999;
    border-radius: 4px;
    font-size: 0.8rem;
    text-decoration: none;
    padding: 0.4rem 1.5rem;
    transition: ease-in 0.15s;
  }

  .nuxtLink:hover {
    opacity: 60%;
  }
</style>