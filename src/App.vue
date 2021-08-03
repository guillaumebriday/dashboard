<template>
<div class="relative bg-gray-50 py-20 px-5">
  <div class="relative max-w-6xl mx-auto">
    <div class="grid gap-5 mx-auto md:grid-cols-2 lg:grid-cols-3">
        <Card
          v-for="project in projects"
          :project="project"
          :user="project.user || user"
          :key="project.name"
        />
    </div>
  </div>
</div>
</template>

<script>
import Card from './components/Card'

export default {
  components: {
    Card
  },

  data () {
    return {
      user: 'guillaumebriday',
      projects: [
        {
          name: 'laravel-blog',
          travis: 'laravel-blog'
        },
        { name: 'traefik-docker-ansible' },
        {
          name: 'todolist-backend-laravel',
          gitlab: 'todolist-backend-laravel'
        },
        {
          name: 'todolist-frontend-vuejs',
          netlify: '68286221-cb5f-4960-834f-0ae250395090',
          travis: 'todolist-frontend-vuejs'
        },
        {
          name: 'vue-scroll-progress-bar',
          npm: '@guillaumebriday/vue-scroll-progress-bar',
          netlify: '63086bf9-f804-451e-9319-052191432063'
        },
        {
          name: 'jsonapi-scopes',
          gem: 'jsonapi-scopes'
        },
        {
          name: 'custom-element-password-toggle',
          npm: 'custom-element-password-toggle',
          netlify: 'f48191db-a459-4ab4-849f-10ea970915af',
          workflows: [
            'Test',
            'Lint'
          ]
        },
        {
          name: 'guillaumebriday.fr',
          netlify: 'f1ff9daf-4123-4b27-9aab-761073812859'
        },
        {
          name: 'json-api-response-converter',
          npm: 'json-api-response-converter'
        },
        {
          name: 'webpack-boilerplate',
          netlify: 'b4f7398b-780c-42e8-8a3e-080c497fda4e'
        },
        {
          name: 'docker-ruby-node',
          docker: 'guillaumebriday/ruby-node'
        },
        {
          name: 'todolist-frontend-nuxt',
          netlify: '61117a85-2c1d-4308-be10-3c77413e8a74',
          travis: 'todolist-frontend-nuxt'
        },
        {
          name: 'traefik-custom-error-pages',
          docker: 'guillaumebriday/traefik-custom-error-pages',
          netlify: '64de9cea-fa16-4f76-b5b8-a1abb5eb4e2f'
        },
        {
          name: 'youarenotfacebook',
          netlify: '80093602-8732-45c2-bbb2-3eae48ba6632'
        },
        {
          name: 'lobsters-docker',
          docker: 'guillaumebriday/lobsters-docker'
        },
        {
          name: 'rails-vue-cli',
          docker: 'guillaumebriday/rails-vue-cli'
        },
        { name: 'selfhosted-services' },
        { name: 'rails-tailwindcss-starter' },
        { name: 'traefik-file-config-example' },
        { name: 'insomnia-telegram-workspace' },
        { name: 'homelab-docker-ansible' },
        { name: 'stimulus-content-loader', npm: 'stimulus-content-loader', user: 'stimulus-components' },
        { name: 'stimulus-textarea-autogrow', npm: 'stimulus-textarea-autogrow', user: 'stimulus-components' },
        { name: 'stimulus-checkbox-select-all', npm: 'stimulus-checkbox-select-all', user: 'stimulus-components' },
        { name: 'stimulus-rails-nested-form', npm: 'stimulus-rails-nested-form', user: 'stimulus-components' },
        { name: 'stimulus-reveal-controller', npm: 'stimulus-reveal-controller', user: 'stimulus-components' },
        { name: 'stimulus-timeago', npm: 'stimulus-timeago', user: 'stimulus-components' },
        { name: 'stimulus-sortable', npm: 'stimulus-sortable', user: 'stimulus-components' },
        { name: 'stimulus-popover', npm: 'stimulus-popover', user: 'stimulus-components' },
        { name: 'stimulus-remote-rails', npm: 'stimulus-remote-rails', user: 'stimulus-components' },
        { name: 'stimulus-character-counter', npm: 'stimulus-character-counter', user: 'stimulus-components' },
        { name: 'stimulus-animated-number', npm: 'stimulus-animated-number', user: 'stimulus-components' },
        { name: 'stimulus-lightbox', npm: 'stimulus-lightbox', user: 'stimulus-components' },
        { name: 'stimulus-scroll-progress', npm: 'stimulus-scroll-progress', user: 'stimulus-components' },
        { name: 'stimulus-carousel', npm: 'stimulus-carousel', user: 'stimulus-components' },
        { name: 'stimulus-rails-autosave', npm: 'stimulus-rails-autosave', user: 'stimulus-components' },
        { name: 'stimulus-scroll-to', npm: 'stimulus-scroll-to', user: 'stimulus-components' },
        { name: 'stimulus-chartjs', npm: 'stimulus-chartjs', user: 'stimulus-components' },
        { name: 'stimulus-prefetch', npm: 'stimulus-prefetch', user: 'stimulus-components' },
        { name: 'stimulus-clipboard', npm: 'stimulus-clipboard', user: 'stimulus-components' },
        { name: 'stimulus-read-more', npm: 'stimulus-read-more', user: 'stimulus-components' },
        { name: 'stimulus-scroll-reveal', npm: 'stimulus-scroll-reveal', user: 'stimulus-components' },
        { name: 'stimulus-places-autocomplete', npm: 'stimulus-places-autocomplete', user: 'stimulus-components' },
        { name: 'stimulus-notification', npm: 'stimulus-notification', user: 'stimulus-components' },
        { name: 'stimulus-dropdown', npm: 'stimulus-dropdown', user: 'stimulus-components' },
      ]
    }
  }
}
</script>

<style>
body {
  @apply bg-gray-200;
}
</style>

<style src="./assets/tailwind.css">
