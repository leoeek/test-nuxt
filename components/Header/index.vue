<template>
  <nav class="bg-gray-800">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-16">
        <div class="flex items-center">

          <div class="flex-shrink-0">
            <img
              class="h-8 w-8"
              src="https://tailwindui.com/img/logos/workflow-mark-indigo-400.svg"
              alt="Só mais um icone legal do Tailwind ;)"
            >
          </div>

          <div class="hidden md:block">
            <div class="ml-10 flex items-baseline">
              <nuxt-link
                to="/"

                class="px-3 py-2 rounded-md text-sm font-medium text-white bg-gray-900 focus:outline-none focus:text-white focus:bg-gray-700"
              >
                Home
              </nuxt-link>

              <nuxt-link
                to="/sobre"
                class="ml-4 px-3 py-2 rounded-md text-sm font-medium text-gray-300 hover:text-white hover:bg-gray-700 focus:outline-none
                focus:text-white focus:bg-gray-700"
              >
                Sobre
              </nuxt-link>
            </div>
          </div>
        </div>
        <div class="hidden md:block">
          <div class="ml-4 flex items-center md:ml-6">

            <div class="ml-3 relative">
              <div>
                <button
                  class="max-w-xs flex items-center text-sm rounded-full text-white focus:outline-none focus:shadow-solid"
                  id="user-menu"
                  aria-label="O cara"
                  aria-haspopup="true"
                >
                  <img
                    class="h-8 w-8 rounded-full"
                    src="https://www.superherodb.com/pictures2/portraits/10/100/639.jpg"
                    alt
                  >
                </button>
              </div>

            </div>
          </div>
        </div>

      </div>
    </div>

  </nav>
</template>
