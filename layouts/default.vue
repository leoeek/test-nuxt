<template>
  <div>
    <div>

      <Header />

      <main class="bg-gray-50">
        <div class="max-w-7xl mx-auto py-6 sm:px-6 lg:px-8 ">
          <div class="px-4 py-6 sm:px-0">
            <div class="h-auto">

              <Nuxt />

            </div>
          </div>
        </div>
      </main>
    </div>
  </div>
</template>

<script>
import Header from '../components/Header'

export default {
  components: {
    Header
  }
}
</script>
