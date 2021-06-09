<template>
  <div>
    <div class="flex justify-center content-center">
      <div class="flex flex-2">
        <input
          name="search"
          class="border border-2 rounded-r px-4 py-2 w-full shadow"
          type="search"
          v-model="search"
          placeholder="Pesquise aqui..."
        />

        <button
          type="button"
          class="text-sm border border-2 rounded-l px-4 py-2 bg-gray-300 whitespace-no-wrap"
          @click="find"
        >
          <svg
          version="1.1"
          class="h-4 text-dark"
          xmlns="http://www.w3.org/2000/svg"
          xmlns:xlink="http://www.w3.org/1999/xlink"
          x="0px"
          y="0px"
          viewBox="0 0 52.966 52.966"
          style="enable-background: new 0 0 52.966 52.966"
          xml:space="preserve"
        >
          <path
            d="M51.704,51.273L36.845,35.82c3.79-3.801,6.138-9.041,6.138-14.82c0-11.58-9.42-21-21-21s-21,9.42-21,21s9.42,21,21,21
            c5.083,0,9.748-1.817,13.384-4.832l14.895,15.491c0.196,0.205,0.458,0.307,0.721,0.307c0.25,0,0.499-0.093,0.693-0.279
            C52.074,52.304,52.086,51.671,51.704,51.273z M21.983,40c-10.477,0-19-8.523-19-19s8.523-19,19-19s19,8.523,19,19
            S32.459,40,21.983,40z"
          />
        </svg>
        </button>
      </div>
    </div>

    <Heros
      :heros="heros"
      :isShow="isShow"
    />
  </div>
</template>

<script>
import Heros from '../components/Heros'

export default {
  components: {
    Heros
  },
  data () {
    return {
      search: '',
      isShow: false,
      heros: []
    }
  },
  methods: {
    async find () {
      this.isShow = false
      const search = encodeURI(this.search)
      await this.$axios
        .get(`search/${search}`)
        .then((res) => {
          this.heros = res.data.results
          this.isShow = true
        })
    }
  }
}
</script>
