<template>
  <nav class="fixed inline-flex justify-around z-40 top-0 inset-x-0 pt-3 px-3" aria-label="Main Menu">
    <a class="logo">
      <img src="/assets/karli/ks-1-white.png" class="logo-image image" alt="karli sensibello" />
    </a>

    <ul class="flex justify-end">
      <li class="">
        <nuxt-link class="btn-nav block" to="/">Home</nuxt-link>
      </li>
      <li class="">
        <nuxt-link class="btn-nav block" to="/about">About</nuxt-link>
      </li>
      <li class="">
        <nuxt-link class="btn-nav block" to="/projects">Projects</nuxt-link>
      </li>
      <li class="">
        <nuxt-link class="btn-nav block" to="/resume">Resume</nuxt-link>
      </li>
      <li class="">
        <nuxt-link class="btn-nav block" to="/contact">Contact</nuxt-link>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: 'Header',
}
</script>

<style lang="postcss" scoped>
.logo {
  .logo-image {
    width: 100%;
    max-width: 200px;
  }
}

.scrim-bg {
  &::before {
    content: '';
    z-index: -1;
    background-color: var(--bg);
    @apply absolute bottom-0 inset-x-0 h-12 mb-4 transition-colors duration-200 ease-in-out;
  }
  &::after {
    content: '';
    z-index: -1;
    opacity: 1;
    animation: fadeIn1 500ms ease-in-out;
    @apply pointer-events-none absolute bottom-0 inset-x-0 h-16 -mb-12;
    background: linear-gradient(to bottom, #111827, cubic-bezier(0.15, 0, 0.45, 1), transparent);
  }
}
.nuxt-link-exact-active {
}

.light {
  & .scrim-bg {
    &::after {
      animation-name: fadeIn2;
      background: linear-gradient(to bottom, #e5e7eb, cubic-bezier(0.15, 0, 0.45, 1), transparent);
    }
  }
  & .nuxt-link-exact-active {
    @apply text-primary-700 border-gray-600 bg-gray-100;
  }
}

/* Need two because of smoother switching between color modes */
@keyframes fadeIn1 {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
@keyframes fadeIn2 {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
</style>
