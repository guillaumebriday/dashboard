<template>
  <div class="flex flex-col rounded-lg shadow-lg overflow-hidden">
    <div class="flex-1 bg-white p-6">
      <h3 class="mt-2 text-xl leading-7 font-semibold text-gray-900">
        <a :href="`https://github.com/${repo}`" class="flex items-center">

          <svg
            fill="none"
            stroke="currentColor"
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            viewBox="0 0 24 24"
            class="mr-2 w-4 h-4"
          >
            <path
              d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4M14 4h6m0 0v6m0-6L10 14"
            />
          </svg>
          {{ project.name }}
        </a>
      </h3>

      <p class="mt-3">
        <img v-for="src in github" :src="src" :key="src" class="badge" />
        <img v-for="src in workflows" :src="src" :key="src" class="badge" />
        <img v-for="src in npm" :src="src" :key="src" class="badge" />
        <img v-for="src in gems" :src="src" :key="src" class="badge" />
        <img v-for="src in docker" :src="src" :key="src" class="badge" />

        <img v-if="project.gitlab" :src="`https://gitlab.com/${user}/${project.gitlab}/badges/master/pipeline.svg`" class="badge" />
        <img v-if="project.travis" :src="`https://travis-ci.org/${user}/${project.travis}.svg?branch=master`" class="badge" />
        <img v-if="project.netlify" :src="`https://img.shields.io/netlify/${project.netlify}`" class="badge" />
      </p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    user: {
      type: String,
      required: true
    },

    project: {
      type: Object,
      required: true
    }
  },

  computed: {
    repo () {
      const name = this.project.github || this.project.name

      return `${this.user}/${name}`
    },

    workflows () {
      if (!this.project.workflows) return []

      return this.project.workflows.map(workflow => `https://github.com/${this.repo}/workflows/${workflow}/badge.svg`)
    },

    github () { return this.buildBadges('github', ['stars', 'forks', 'issues', 'issues-pr', 'license'], this.repo) },
    npm () { return this.buildBadges('npm', ['v', 'dt'], this.project.npm) },
    gems () { return this.buildBadges('gem', ['v', 'dt'], this.project.gem) },
    docker () { return this.buildBadges('docker', ['pulls', 'stars'], this.project.docker) }
  },

  methods: {
    buildBadges (service, badges, repository) {
      if (!repository) return []

      return badges.map(badge => `https://img.shields.io/${service}/${badge}/${repository}.svg`)
    }
  }
}
</script>

<style>
.badge {
  @apply inline-block ml-2 mb-2;
}
</style>
