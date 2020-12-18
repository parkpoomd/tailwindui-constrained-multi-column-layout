<template>
  <div class="min-h-screen flex flex-col">
    <!-- Navbar -->
    <nav class="flex-shrink-0 bg-indigo-700">
      <div class="max-w-7xl mx-auto px-2 sm:px-4 lg:px-8">
        <div class="flex items-center justify-between h-16">
          <!-- Logo section -->
          <div
            class="flex items-center flex-shrink-0 px-2 lg:px-0 xl:w-64 space-x-1"
          >
            <svg
              class="h-12 w-12 text-indigo-400"
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M17.657 18.657A8 8 0 016.343 7.343S7 9 9 10c0-2 .5-5 2.986-7C14 5 16.09 5.777 17.656 7.343A7.975 7.975 0 0120 13a7.975 7.975 0 01-2.343 5.657z"
              />
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M9.879 16.121A3 3 0 1012.015 11L11 14H9c0 .768.293 1.536.879 2.121z"
              />
            </svg>
            <span class="text-white text-2xl font-bold tracking-wide"
              >workflow</span
            >
          </div>

          <!-- Search section -->
          <div class="flex-1 flex justify-center lg:justify-end">
            <div class="w-full px-2 lg:px-6">
              <label for="search" class="sr-only">Search projects</label>
              <div class="relative text-indigo-300 focus-within:text-gray-400">
                <div
                  class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none"
                >
                  <svg class="h-5 w-5" fill="currentColor" viewBox="0 0 20 20">
                    <path
                      fill-rule="evenodd"
                      d="M8 4a4 4 0 100 8 4 4 0 000-8zM2 8a6 6 0 1110.89 3.476l4.817 4.817a1 1 0 01-1.414 1.414l-4.816-4.816A6 6 0 012 8z"
                      clip-rule="evenodd"
                    />
                  </svg>
                </div>
                <input
                  id="search"
                  class="block w-full pl-10 pr-3 py-2 border border-transparent rounded-md leading-5 bg-indigo-400 bg-opacity-25 text-indigo-300 placeholder-indigo-300 focus:outline-none focus:bg-white focus:placeholder-gray-400 focus:text-gray-900 sm:text-sm transition duration-150 ease-in-out"
                  placeholder="Search projects"
                  type="search"
                />
              </div>
            </div>
          </div>

          <div class="flex lg:hidden">
            <!-- Mobile menu button -->
            <button
              @click="isMobileMenuOpen = !isMobileMenuOpen"
              class="inline-flex items-center justify-center p-2 rounded-md text-indigo-400 hover:text-white hover:bg-indigo-600 focus:outline-none focus:text-white transition duration-150 ease-in-out"
            >
              <svg
                class="block h-6 w-6"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M4 6h16M4 12h8m-8 6h16"
                />
              </svg>
            </button>
          </div>

          <!-- Links section -->
          <div class="hidden lg:block lg:w-80">
            <div class="flex items-center justify-end">
              <div class="flex">
                <a
                  href="#"
                  class="px-3 py-2 rounded-md text-sm leading-5 font-medium text-indigo-200 hover:text-white focus:outline-none focus:text-white focus:bg-indigo-600 transition duration-150 ease-in-out"
                  >Documentation</a
                >
                <a
                  href="#"
                  class="px-3 py-2 rounded-md text-sm leading-5 font-medium text-indigo-200 hover:text-white focus:outline-none focus:text-white focus:bg-indigo-600 transition duration-150 ease-in-out"
                  >Support</a
                >
              </div>
              <!-- Profile dropdown -->
              <div class="ml-4 relative flex-shrink-0">
                <div>
                  <button
                    @click="isUserMenuOpen = !isUserMenuOpen"
                    class="flex text-sm rounded-full text-white focus:outline-none focus:ring-2 focus:ring-white transition duration-150 ease-in-out"
                    id="user-menu"
                    aria-label="User menu"
                    aria-haspopup="true"
                  >
                    <img
                      class="h-8 w-8 rounded-full"
                      src="https://images.unsplash.com/photo-1517365830460-955ce3ccd263?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=256&h=256&q=80"
                      alt=""
                    />
                  </button>
                </div>
                <!-- Profile dropdown panel -->
                <transition
                  enter-active-class="transition ease-out duration-100"
                  enter-from-class="transform opacity-0 scale-95"
                  enter-to-class="transform opacity-100 scale-100"
                  leave-active-class="transition ease-in duration-75"
                  leave-from-class="transform opacity-100 scale-100"
                  leave-to-class="transform opacity-0 scale-95"
                >
                  <div
                    v-show="isUserMenuOpen"
                    class="origin-top-right absolute right-0 mt-2 w-48 rounded-md shadow-lg"
                  >
                    <div class="py-1 rounded-md bg-white shadow-sm">
                      <a
                        href="#"
                        class="block px-4 py-2 text-sm leading-5 text-gray-700 hover:bg-gray-100 focus:outline-none focus:bg-gray-100 transition duration-150 ease-in-out"
                        role="menuitem"
                        >View Profile</a
                      >
                      <a
                        href="#"
                        class="block px-4 py-2 text-sm leading-5 text-gray-700 hover:bg-gray-100 focus:outline-none focus:bg-gray-100 transition duration-150 ease-in-out"
                        role="menuitem"
                        >Settings</a
                      >
                      <a
                        href="#"
                        class="block px-4 py-2 text-sm leading-5 text-gray-700 hover:bg-gray-100 focus:outline-none focus:bg-gray-100 transition duration-150 ease-in-out"
                        role="menuitem"
                        >Sign out</a
                      >
                    </div>
                  </div>
                </transition>
                <!-- /Profile dropdown panel -->
              </div>
            </div>
          </div>
          <!-- /Links section -->
        </div>
      </div>

      <!-- Mobile menu -->
      <div v-if="isMobileMenuOpen" class="lg:hidden">
        <div class="px-2 pt-2 pb-3 space-y-1">
          <a
            href="#"
            class="block px-3 py-2 rounded-md text-base font-medium text-indigo-200 hover:text-indigo-100 hover:bg-indigo-600 focus:outline-none focus:text-white focus:bg-indigo-600 transition duration-150 ease-in-out"
            >Documentation</a
          >
          <a
            href="#"
            class="block px-3 py-2 rounded-md text-base font-medium text-indigo-200 hover:text-indigo-100 hover:bg-indigo-600 focus:outline-none focus:text-white focus:bg-indigo-600 transition duration-150 ease-in-out"
            >Support</a
          >
        </div>
        <div class="pt-4 pb-3 border-t border-indigo-800">
          <div class="px-2 space-y-1">
            <a
              href="#"
              class="block px-3 py-2 rounded-md text-base font-medium text-indigo-200 hover:text-indigo-100 hover:bg-indigo-600 focus:outline-none focus:text-white focus:bg-indigo-600 transition duration-150 ease-in-out"
            >
              Your Profile
            </a>
            <a
              href="#"
              class="block px-3 py-2 rounded-md text-base font-medium text-indigo-200 hover:text-indigo-100 hover:bg-indigo-600 focus:outline-none focus:text-white focus:bg-indigo-600 transition duration-150 ease-in-out"
            >
              Settings
            </a>
            <a
              href="#"
              class="block px-3 py-2 rounded-md text-base font-medium text-indigo-200 hover:text-indigo-100 hover:bg-indigo-600 focus:outline-none focus:text-white focus:bg-indigo-600 transition duration-150 ease-in-out"
            >
              Sign out
            </a>
          </div>
        </div>
      </div>
      <!-- /Mobile menu -->
    </nav>
    <!-- /Navbar -->

    <!-- 3 column wrapper -->
    <div class="flex-grow w-full max-w-7xl mx-auto lg:flex">
      <!-- Left sidebar & main wrapper -->
      <div class="flex-1 min-w-0 bg-white xl:flex xl:pl-8">
        <div
          class="xl:flex-shrink-0 xl:w-64 xl:border-r xl:border-gray-200 bg-white"
        >
          <div class="pl-4 pr-6 py-6 sm:pl-6 lg:pl-8 xl:pl-0">
            <!-- Dashboard header -->
            <div class="flex items-center justify-between">
              <div class="flex-1 space-y-8">
                <div
                  class="block space-y-8 sm:space-y-0 sm:flex sm:justify-between sm:items-center xl:block xl:space-x-0 xl:space-y-8"
                >
                  <!-- Profile -->
                  <div class="flex items-center space-x-3">
                    <div class="flex-shrink-0 h-12 w-12">
                      <img
                        class="h-12 w-12 rounded-full"
                        :src="user.avatar"
                        alt="user profile"
                      />
                    </div>
                    <div class="space-y-1">
                      <div class="text-sm leading-5 font-medium text-gray-900">
                        {{ user.name }}
                      </div>
                      <a
                        :href="user.githubUrl"
                        class="group flex items-center space-x-2"
                      >
                        <svg
                          class="h-5 w-5 text-gray-400 group-hover:text-gray-500"
                          fill="currentColor"
                          viewBox="0 0 20 20"
                        >
                          <path
                            fill-rule="evenodd"
                            d="M10 1C5.03 1 1 5.025 1 9.991c0 3.973 2.579 7.343 6.155 8.532.45.082.614-.195.614-.434 0-.213-.007-.779-.012-1.529-2.503.543-3.031-1.205-3.031-1.205-.41-1.039-1-1.316-1-1.316-.817-.557.062-.546.062-.546.903.063 1.378.927 1.378.927.803 1.374 2.107.977 2.62.747.082-.581.314-.977.571-1.202-1.998-.227-4.1-.998-4.1-4.444 0-.981.351-1.784.927-2.412-.093-.228-.402-1.142.089-2.38 0 0 .755-.242 2.474.922.718-.2 1.488-.3 2.253-.303a8.638 8.638 0 012.253.303c1.719-1.164 2.473-.922 2.473-.922.491 1.238.182 2.152.09 2.38.577.628.925 1.43.925 2.412 0 3.454-2.105 4.214-4.11 4.437.323.277.611.826.611 1.665 0 1.202-.01 2.171-.01 2.466 0 .24.162.52.618.433 3.574-1.192 6.15-4.56 6.15-8.53C19 5.024 14.97 1 10 1z"
                            clip-rule="evenodd"
                          />
                        </svg>
                        <span
                          class="text-sm text-gray-500 leading-5 font-medium group-hover:text-gray-900"
                          >{{ user.username }}</span
                        >
                      </a>
                    </div>
                  </div>
                  <!-- Action buttons -->
                  <div
                    class="flex flex-col space-y-3 space-x-0 sm:space-y-0 sm:space-x-3 sm:flex-row xl:flex xl:flex-col xl:space-y-3 xl:space-x-0"
                  >
                    <span class="inline-flex rounded-md shadow-sm">
                      <button
                        type="button"
                        class="w-full inline-flex items-center justify-center px-4 py-2 border text-sm leading-5 font-medium rounded-md focus:outline-none transition ease-in-out duration-150 border-transparent text-white bg-indigo-600 hover:bg-indigo-500 focus:border-indigo-700 focus:ring active:bg-indigo-700"
                      >
                        New Project
                      </button>
                    </span>
                    <span class="inline-flex rounded-md shadow-sm">
                      <button
                        type="button"
                        class="w-full inline-flex items-center justify-center px-4 py-2 border text-sm leading-5 font-medium rounded-md focus:outline-none transition ease-in-out duration-150 border-gray-300 text-gray-700 bg-white hover:text-gray-500 focus:border-blue-300 focus:ring active:text-gray-800 active:bg-gray-50"
                      >
                        Invite Team
                      </button>
                    </span>
                  </div>
                </div>
                <!-- Meta info -->
                <div
                  class="flex flex-col space-y-6 space-x-0 sm:flex-row sm:space-y-0 sm:space-x-8 xl:flex xl:flex-col xl:space-y-6 xl:space-x-0"
                >
                  <span class="flex items-center space-x-2">
                    <svg
                      class="h-5 w-5 text-gray-400"
                      xmlns="http://www.w3.org/2000/svg"
                      viewBox="0 0 20 20"
                      fill="currentColor"
                    >
                      <path
                        fill-rule="evenodd"
                        d="M6.267 3.455a3.066 3.066 0 001.745-.723 3.066 3.066 0 013.976 0 3.066 3.066 0 001.745.723 3.066 3.066 0 012.812 2.812c.051.643.304 1.254.723 1.745a3.066 3.066 0 010 3.976 3.066 3.066 0 00-.723 1.745 3.066 3.066 0 01-2.812 2.812 3.066 3.066 0 00-1.745.723 3.066 3.066 0 01-3.976 0 3.066 3.066 0 00-1.745-.723 3.066 3.066 0 01-2.812-2.812 3.066 3.066 0 00-.723-1.745 3.066 3.066 0 010-3.976 3.066 3.066 0 00.723-1.745 3.066 3.066 0 012.812-2.812zm7.44 5.252a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z"
                        clip-rule="evenodd"
                      />
                    </svg>
                    <span class="text-sm text-gray-500 leading-5 font-medium">
                      Pro Member
                    </span>
                  </span>
                  <span class="flex items-center space-x-2">
                    <svg
                      class="h-5 w-5 text-gray-400"
                      xmlns="http://www.w3.org/2000/svg"
                      viewBox="0 0 20 20"
                      fill="currentColor"
                    >
                      <path
                        d="M7 3a1 1 0 000 2h6a1 1 0 100-2H7zM4 7a1 1 0 011-1h10a1 1 0 110 2H5a1 1 0 01-1-1zM2 11a2 2 0 012-2h12a2 2 0 012 2v4a2 2 0 01-2 2H4a2 2 0 01-2-2v-4z"
                      />
                    </svg>
                    <span class="text-sm text-gray-500 leading-5 font-medium"
                      >{{ user.projectCount }} Projects</span
                    >
                  </span>
                </div>
              </div>
            </div>
            <!-- /Dashboard header -->
          </div>
        </div>
      </div>
    </div>
    <!-- /3 column wrapper -->
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      isUserMenuOpen: false,
      isMobileMenuOpen: false,
      user: {
        name: 'Debbie Lewis',
        username: 'debbielewis',
        avatar:
          'https://images.unsplash.com/photo-1517365830460-955ce3ccd263?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=256&h=256&q=80',
        projectCount: 9,
        membership: 'Pro',
        githubUrl: 'https://example.com/debbielewis',
      },
    };
  },
};
</script>
