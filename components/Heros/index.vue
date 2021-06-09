<template>
  <div>
    <div
      v-if="isShow && !heros"
      class="text-center font-medium text-sm p-8"
    >
      Ops! Nenhum Super encontrado :(
    </div>

    <div
      v-else
      class="grid gap-4 grid-cols-4 pt-5"
    >

      <div
        v-if="isShowing"
        class="text-center font-medium text-sm p-8"
      >
        Carregando....
      </div>

      <div
        v-else
        class="p-2 flex-1"
        v-for="hero in heros"
        :key="hero.id"
      >
        <div class="max-w-sm rounded overflow-hidden shadow-lg mb-4 bg-white border-1 h-300 min-h-full">
          <div class="flex justify-center p-3">
            <img
              style="height: 200px"
              class="rounded-lg"
              :src="hero.image['url']"
              :alt="`Foto de ${hero.name }`"
              :title="`Foto de ${hero.name }`"
            >
          </div>

          <div class="px-6 py-4 pb-2 text-center">
            <div
              @click="$refs.modalHero.open(hero)"
              class="font-bold text-2xl mb-2 cursor-pointer"
            >
              {{ hero.name }}
            </div>
            <p
              class="text-gray-700 text-base"
            >
            {{ hero.biography['full-name'] }}
            </p>
          </div>

          <div class="px-6 py-4 text-center">
            <button
              class="mt-3 w-full inline-flex justify-center rounded-md border border-gray-300 shadow-sm px-4 py-2 bg-white text-base font-medium text-gray-700 hover:bg-gray-50 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500 sm:mt-0 sm:ml-3 sm:w-auto sm:text-sm"
              @click="$refs.modalHero.open(hero)"
              type="button"
            >Detalhe</button>
          </div>
        </div>
      </div>
    </div>

    <Modal ref="modalHero" />
  </div>
</template>

<script>
import Modal from '../Modal/ModalHero.vue'

export default {
  props: ['heros', 'isShow'],
  components: {
    Modal
  },
  data () {
    return {
      isShowing: true
    }
  },
  mounted () {
    this.isShowing = false
  },
  methods: {
    detail ({ id }) {
      alert(id)
    },
    open () {
      alert('oi')
    }
  }
}
</script>

<style scoped>
.description {
  display: -webkit-box;
  -webkit-line-clamp: 9;
  -webkit-box-orient: vertical;
  overflow: hidden;
  text-overflow: ellipsis;
}
</style>
