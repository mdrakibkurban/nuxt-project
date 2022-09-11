<template>

  <div>

      <div class="p-4">
         <vue-slick-carousel class="slider" :arrows="false" :dots="true">
         <div class="slider-bg-color rounded-2xl pt-8">
              <div class="container mx-auto px-12">
                <div class="flex items-center">
                  <div class="w-1/2 mr-6 ">
                       <p class="font-size-32 text-green-500 mb-4">Save up 30% off</p>
                       <h2 class="text-7xl font-bold font-color mb-6">Bengal Vegetable farm Organic 100%</h2>
                       <p class="font-size-22 mb-8">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vehicula faucibus massa est elit maecenas.</p>
                        <nuxt-link to="" class="bg-green-500 rounded-full px-6 py-2 text-white display: inline-block text-base
                        ">Shop Now</nuxt-link>
                 </div>
                  <div class="w-1/2 flex justify-end ">
                    <img width="500px" src="~/assets/img/person.png" alt="">
                  </div>
                </div>
              </div>
         </div>

         <div class="slider-bg-color rounded-2xl pt-8">
              <div class="container mx-auto px-12">
                <div class="flex items-center">
                  <div class="w-1/2 mr-6 ">
                       <p class="font-size-32 text-green-500 mb-4">Save up 40% off</p>
                       <h2 class="text-7xl font-bold font-color mb-6">Bengal Vegetable farm Organic 100%</h2>
                       <p class="font-size-22 mb-8">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vehicula faucibus massa est elit maecenas.</p>
                        <nuxt-link to="" class="bg-green-500 rounded-full px-6 py-2 text-white display: inline-block text-base
                        ">Shop Now</nuxt-link>
                 </div>
                  <div class="w-1/2 flex justify-end ">
                    <img width="500px" src="~/assets/img/person.png" alt="">
                  </div>
                </div>
              </div>
         </div>


         <div class="slider-bg-color rounded-2xl pt-8">
              <div class="container mx-auto px-12">
                <div class="flex items-center">
                  <div class="w-1/2 mr-6 ">
                       <p class="font-size-32 text-green-500 mb-4">Save up 50% off</p>
                       <h2 class="text-7xl font-bold font-color mb-6">Bengal Vegetable farm Organic 100%</h2>
                       <p class="font-size-22 mb-8">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vehicula faucibus massa est elit maecenas.</p>
                        <nuxt-link to="" class="bg-green-500 rounded-full px-6 py-2 text-white display: inline-block text-base
                        ">Shop Now</nuxt-link>
                 </div>
                  <div class="w-1/2 flex justify-end ">
                    <img width="500px" src="~/assets/img/person.png" alt="">
                  </div>
                </div>
              </div>
         </div>
        </vue-slick-carousel>

         <div class="container mx-auto pt-10">
               <h3 class="text-3xl mb-6 font-medium">Search by Category</h3>
               <div class="flex items-center mb-10">
                  <div style="height:2px;" class="w-32 bg-green-500"></div>
                  <div style="height:2px;" class="w-full bg-gray-200"></div>
               </div>

               <vue-slick-carousel class="category-carousel mb-10" v-bind="categorySettings">
                   <div class="bg-gray-200 p-4">
                     <div class="h-32 flex justify-center items-center">
                            <img src="~/assets/img/Groceries.png" alt="">
                     </div>
                     <h4 class="text-xl text-center">Groceries</h4>
                   </div>

                  <div class="bg-gray-200 p-4">
                     <div class="h-32 flex justify-center items-center">
                            <img src="~/assets/img/Fish.png" alt="">
                     </div>
                     <h4 class="text-xl text-center">Fish</h4>
                   </div>

                  <div class="bg-gray-200 p-4">
                     <div class="h-32 flex justify-center items-center">
                            <img src="~/assets/img/Meat.png" alt="">
                     </div>
                     <h4 class="text-xl text-center">Meat</h4>
                  </div>

                  <div class="bg-gray-200 p-4">
                     <div class="h-32 flex justify-center items-center">
                            <img src="~/assets/img/Vegetables.png" alt="">
                     </div>
                     <h4 class="text-xl text-center">Vegetables</h4>
                  </div>

                  <div class="bg-gray-200 p-4">
                     <div class="h-32 flex justify-center items-center">
                            <img src="~/assets/img/fruits.png" alt="">
                     </div>
                     <h4 class="text-xl text-center">Fruits</h4>
                  </div>

                  <div class="bg-gray-200 p-4">
                     <div class="h-32 flex justify-center items-center">
                            <img src="~/assets/img/Vegetables.png" alt="">
                     </div>
                     <h4 class="text-xl text-center">Vegetables</h4>
                  </div>


                  <div class="bg-gray-200 p-4">
                     <div class="h-32 flex justify-center items-center">
                            <img src="~/assets/img/fruits.png" alt="">
                     </div>
                       <h4 class="text-xl text-center">Fruits</h4>
                  </div>




                       <template #prevArrow="arrowOption">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                          <path stroke-linecap="round" stroke-linejoin="round" d="M15 19l-7-7 7-7" />
                        </svg>
                      </template>

                      <template #nextArrow="arrowOption">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                          <path stroke-linecap="round" stroke-linejoin="round" d="M9 5l7 7-7 7" />
                        </svg>
                      </template>

              </vue-slick-carousel>



           <div class="flex -mx-6 mb-10">
                 <div class="w-1/2 px-6">
                    <div class="bg-image-1 bg-cover bg-center p-14 rounded">
                         <div class="w-1/2 mr-4">
                          <h3 class="text-2xl mb-4 text-red-400">Buy 1 Get 1</h3>
                          <h1 class="text-4xl mb-6 font-bold text-black">Fresh Fruits Collection</h1>
                          <nuxt-link to="" class="bg-white rounded-full px-6 py-2 text-red-500 display: inline-block text-base
                                ">Order Now
                        </nuxt-link>
                         </div>
                    </div>
                 </div>


                 <div class="w-1/2 px-6">
                    <div class="bg-image-2 bg-cover bg-center p-14 rounded">
                         <div class="w-1/2">
                          <h3 class="text-2xl mb-4 text-red-400">Buy 1 Get 1</h3>
                          <h1 class="text-4xl mb-6 font-bold text-black">Fresh Fruits Collection</h1>
                          <nuxt-link to="" class="bg-white rounded-full px-6 py-2 text-red-500 display: inline-block text-base
                                ">Order Now
                        </nuxt-link>
                         </div>
                    </div>
                 </div>
           </div>


            <h3 class="text-3xl mb-6  font-medium">Deals of the Week</h3>
            <div class="flex items-center mb-10">
                <div style="height:2px;" class="w-32 bg-green-500"></div>
                <div style="height:2px;" class="w-full bg-gray-200"></div>
            </div>


            <vue-slick-carousel v-if="dealsOfProduct.length" class="product-carousel mb-10" v-bind="productCarouselSettings">

                <singleProduct v-for="product in dealsOfProduct" :key="product.id" :product="product"/>

                <template #prevArrow="arrowOption">
                  <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
                  </svg>
                </template>

                <template #nextArrow="arrowOption">
                  <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
                  </svg>
                </template>
           </vue-slick-carousel>



        <h3 class="text-3xl mb-6 font-medium">Popular Brands</h3>
          <div class="flex items-center mb-10">
          <div style="height:2px;" class="w-32  bg-green-500"></div>
          <div style="height:2px;" class="w-full  bg-gray-200"></div>
         </div>

          <vue-slick-carousel class="category-carousel mb-16 text-center" v-bind="categorySettings">
            <div class="">
              <div class="h-32 flex justify-center items-center"><img src="~/assets/img/brand-1.png" alt=""></div>
            </div>

            <div class="">
              <div class="h-32 flex justify-center items-center"><img src="~/assets/img/brand-2.png" alt=""></div>
            </div>

            <div class="">
              <div class="h-32 flex justify-center items-center"><img src="~/assets/img/brand-3.png" alt=""></div>
            </div>

            <div class="">
              <div class="h-32 flex justify-center items-center"><img src="~/assets/img/brand-4.png" alt=""></div>
            </div>

            <div class="">
              <div class="h-32 flex justify-center items-center"><img src="~/assets/img/brand-5.png" alt=""></div>
            </div>

            <div class="">
              <div class="h-32 flex justify-center items-center"><img src="~/assets/img/brand-6.png" alt=""></div>
            </div>

            <div class="">
              <div class="h-32 flex justify-center items-center"><img src="~/assets/img/brand-1.png" alt=""></div>
            </div>



            <template #prevArrow="arrowOption">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
              </svg>
            </template>

            <template #nextArrow="arrowOption">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
              </svg>
            </template>
          </vue-slick-carousel>

        </div>
      </div>
  </div>

  </template>

  <script>
    import SingleProduct from "../components/SingleProduct";

    import dealsOfProduct from "assets/deals-of-product.json"
  export default {
    components: {SingleProduct},
     data() {
      return {
         categorySettings:{
            "slidesToShow": 6,
         },
         productCarouselSettings:{
          "slidesToShow": 4,
         },
         brandCarouselSetting:{
            "slidesToShow": 6,
         },

         dealsOfProduct:[]
      }
     },

     mounted(){
        this.dealsOfProduct = dealsOfProduct;
     }
  }
  </script>


