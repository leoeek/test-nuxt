<template>
  <div class="p-4">
    <div class="max-w-sm rounded overflow-hidden shadow-lg mb-4">
      <img
        class="w-full"
        src="https://tailwindcss.com/img/card-top.jpg"
        alt="Sunset in the mountains"
      >
      <div class="px-6 py-4 pb-2">
        <div class="font-bold text-xl mb-2">{{ hero.name }}</div>
        <p
          class="text-gray-700 text-base"
        >
         {{ hero.image }}
        </p>
      </div>
      <div class="px-6 py-4">
        <span class="badge mr-2">{{ hero.name }}</span>
        <span class="badge mr-2">{{ hero.name }}</span>
        <span class="badge">{{ hero.name }}</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      hero: {}
    }
  },
  mounted () {
    this.getHero()
  },
  methods: {
    async getHero () {
      await this.$axios
        .get(this.$route.params.id)
        .then((res) => {
          this.hero = res.data
        })
    }
  }
}
</script>

<style lang="postcss" scoped>
.badge {
  @apply inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700;
  &:hover {
    @apply bg-gray-300;
  }
}
</style>
