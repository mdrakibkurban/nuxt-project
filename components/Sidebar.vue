<template>
  <accordion>
        <accordion-item>
          <!-- This slot will handle the title/header of the accordion and is the part you click on -->
          <template slot="accordion-trigger">
            <h3 class="p-5 rounded-t-xl cursor-pointer flex justify-between bg-green-50">Category
              <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
              </svg>
            </h3>

          </template>
          <!-- This slot will handle all the content that is passed to the accordion -->
          <template slot="accordion-content">
              <div class="border border-t-0 border-gray-50 p-5">
                  <ul>
                    <li>
                      <accordion>
                        <accordion-item>
                          <!-- This slot will handle the title/header of the accordion and is the part you click on -->
                          <template slot="accordion-trigger">
                            <div class="flex justify-between cursor-pointer items-center hover:text-green-600">
                                Fruits
                                <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
                                </svg>
                              </div>
                          </template>
                          <!-- This slot will handle all the content that is passed to the accordion -->
                          <template slot="accordion-content">
                            <ul>
                              <li>
                                <ul class="pl-4 text-sm leading-8 mb-4">
                                  <li><nuxt-link class="hover:text-green-600" to="/">Sub Category</nuxt-link></li>
                                  <li><nuxt-link class="hover:text-green-600" to="/">Sub Category</nuxt-link></li>
                                  <li><nuxt-link class="hover:text-green-600" to="/">Sub Category</nuxt-link></li>
                                  <li><nuxt-link class="hover:text-green-600" to="/">Sub Category</nuxt-link></li>
                                </ul>
                              </li>
                            </ul>
                          </template>
                        </accordion-item>

                      </accordion>
                    </li>
                      <li><nuxt-link class="hover:text-green-600" to="/">Vagetables</nuxt-link></li>
                      <li><nuxt-link class="hover:text-green-600" to="/">Meet</nuxt-link></li>
                  </ul>
              </div>
          </template>
        </accordion-item>




      </accordion>
</template>

<script>
export default {
  name: "Sidebar"
}
</script>

<style scoped>
</style>
