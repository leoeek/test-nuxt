<template>
  <transition name="fade">
    <div v-if="isShow" class="fixed z-10 inset-0 overflow-y-auto" aria-labelledby="modal-title" role="dialog" aria-modal="true">
      <div class="flex items-end justify-center min-h-screen pt-4 px-4 pb-20 text-center sm:block sm:p-0">

        <div class="fixed inset-0 bg-gray-500 bg-opacity-75 transition-opacity" aria-hidden="true"></div>

        <span class="hidden sm:inline-block sm:align-middle sm:h-screen" aria-hidden="true">&#8203;</span>

        <div class="inline-block align-bottom bg-white rounded-lg text-left overflow-hidden shadow-xl transform transition-all sm:my-8 sm:align-middle sm:max-w-lg sm:w-full">
          <div class="bg-white px-4 pt-5 pb-4 sm:p-6 sm:pb-4">
            <div class="sm:flex sm:items-start">

              <div class="mt-3 text-center sm:mt-0 sm:ml-4 sm:text-left">
                <h3 class="text-lg leading-6 font-bold text-gray-900" id="modal-title">
                  {{ hero.name }}
                </h3>
                <div class="mt-2">
                  <div class="m-5 flex justify-center">
                    <img class="w-40" :src="hero.image['url']" />
                  </div>

                  <p class="font-medium mt-4 text-gray-900">Geral</p>
                  <p class="text-sm text-gray-500">
                    Nome: {{ hero.biography['full-name'] }}
                  </p>
                  <p class="text-sm text-gray-500">
                    Nascido em: {{ hero.biography['full-name'] }}
                  </p>
                  <p class="text-sm text-gray-500">
                    Visto primeiro em: {{ hero.biography['first-appearance'] }} <i>({{ hero.biography['publisher'] }})</i>
                  </p>
                  <p class="text-sm text-gray-500">
                    Alteregos: {{ hero.biography['place-of-birth'] }}
                  </p>

                  <p class="font-medium mt-4 text-gray-900">Informações de aparência</p>
                  <p class="text-sm text-gray-500">
                    Gênero: {{ hero.appearance['gender'] }}
                  </p>
                  <p class="text-sm text-gray-500">
                    Raça: {{ hero.appearance['race'] }}
                  </p>
                  <p class="text-sm text-gray-500">
                    Altura: {{ hero.appearance['height'][1] }}
                  </p>
                  <p class="text-sm text-gray-500">
                    Peso: {{ hero.appearance['weight'][1] }}
                  </p>
                  <p class="text-sm text-gray-500">
                    Cor dos Olhos: {{ hero.appearance['eye-color'] }}
                  </p>
                  <p class="text-sm text-gray-500">
                    Cor do cabelo: {{ hero.appearance['hair-color'] }}
                  </p>

                  <p class="font-medium mt-4 text-gray-900">Dados de trabalho</p>
                  <p class="text-sm text-gray-500">
                    Ocupação: {{ hero.work['occupation'] }}
                  </p>
                  <p class="text-sm text-gray-500">
                    Local: {{ hero.work['base'] }}
                  </p>

                  <p class="font-medium mt-4 text-gray-900">Conexões com</p>
                  <p class="text-sm text-gray-500">
                    Grupo: {{ hero.connections['group-affiliation'] }}
                  </p>
                  <p class="text-sm mt-3 text-gray-500">
                    Pessoas: {{ hero.connections['relatives'] }}
                  </p>

                  <p class="font-medium mt-4 text-gray-900">Conhecido também por</p>
                  <p class="text-sm text-gray-500">
                    <span
                      v-for="aliase in hero.biography['aliases']"
                      :key="aliase"
                    >{{ aliase }}</span>
                  </p>
                </div>
              </div>
            </div>
          </div>
          <div class="bg-gray-50 px-4 py-3 sm:px-6 sm:flex sm:flex-row-reverse">
            <button
              @click="close"
              type="button"
              class="mt-3 w-full inline-flex justify-center rounded-md border border-gray-300 shadow-sm px-4 py-2 bg-white text-base font-medium text-gray-700 hover:bg-gray-50 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500 sm:mt-0 sm:ml-3 sm:w-auto sm:text-sm">
              Fechar
            </button>
          </div>
        </div>
      </div>
    </div>
  </transition>
</template>

<script>
export default {
  data () {
    return {
      isShow: false,
      hero: {}
    }
  },
  methods: {
    open (hero) {
      this.isShow = true
      this.hero = hero
    },
    close () {
      this.isShow = false
    }
  }
}
</script>
