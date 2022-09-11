<template>
  <div>
    <div class="container mx-auto">
      <div class="flex -mx-4 mb-10">
        <div class="w-1/4 px-4 flex items-center">
          <div class="min-w-max mr-3">
            <img width="80" src="~/assets/img/customer_support.png" alt="">
          </div>
          <div class="w-full">
            <h3 class="text-lg font-medium mb-2">24 Customer Support</h3>
            <p>Contact us 24 hours</p>
          </div>
        </div>

        <div class="w-1/4 px-4 flex items-center">
          <div class="min-w-max mr-2">
            <img width="80" src="~/assets/img/authentic_products.png" alt="">
          </div>
          <div class="w-full">
            <h3 class="text-lg font-medium mb-2">Authentic Products</h3>
            <p>Contact us 24 hours</p>
          </div>
        </div>

        <div class="w-1/4 px-4 flex items-center">
          <div class="min-w-max mr-3">
            <img width="80" src="~/assets/img/secure.png" alt="">
          </div>
          <div class="w-full">
            <h3 class="text-lg font-medium mb-2">Secure Payment</h3>
            <p>Contact us 24 hours</p>
          </div>
        </div>

        <div class="w-1/4 px-4 flex items-center">
          <div class="min-w-max mr-3">
            <img width="80" src="~/assets/img/best_price.png" alt="">
          </div>
          <div class="w-full">
            <h3 class="text-lg font-medium mb-3">Best Prices & Offers</h3>
            <p>Contact us 24 hours</p>
          </div>
        </div>
      </div>
    </div>

    <div class="bg-gray-200 py-20">
      <div class="container mx-auto">
        <div class="flex">
          <div class="w-3/5 pr-6">
            <Logo />
            <p class="my-6">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla diam ornare nam est gravida. Netus viverra
              rhoncus sit magna sapien ac eget parturient id. Est luctus dapibus quam aliquam in nisl turpis. Elit et
              dictum lacus morbi nec accumsan a in.</p>
              <div class="flex">
                <a class="mr-2" href=""><img src="~/assets/img/apple_play_store.png" alt=""></a>
                <a href=""><img src="~/assets/img/google_play_store.png" alt=""></a>
              </div>
          </div>

          <div class="w-1/5 pl-14">
                <h4 class="font-medium text-2xl mb-6">About Us</h4>
                    <ul class="leading-loose">
                       <li><nuxt-link  to="/">About Karte</nuxt-link></li>
                       <li><nuxt-link  to="/">Contact</nuxt-link></li>
                       <li><nuxt-link  to="/">Career</nuxt-link></li>
                       <li><nuxt-link  to="/">Terms & Conditions</nuxt-link></li>
                       <li><nuxt-link  to="/">Category</nuxt-link></li>
                    </ul>
          </div>

          <div class="w-1/5 pl-14">
               <h4 class="font-medium text-2xl mb-6">Info</h4>
                 <ul class="leading-loose">
                       <li><nuxt-link  to="/">information</nuxt-link></li>
                       <li><nuxt-link  to="/">Shipping </nuxt-link></li>
                       <li><nuxt-link  to="/">Payment Return</nuxt-link></li>
                       <li><nuxt-link  to="/">Blog</nuxt-link></li>
                  </ul>
          </div>

        </div>

        <div class="flex justify-between mt-20 items-center">
             <div class="min-w-max">
               <div class="flex">
                <a class="mr-4 " href=""><img class="w-10" src="~/assets/img/facebook.png" alt=""></a>
                <a class="mr-4" href=""><img class="w-10" src="~/assets/img/Twitter.png" alt=""></a>
                <a class="mr-4" href=""><img class="w-10" src="~/assets/img/skype.png" alt=""></a>
                <a class="mr-4" href=""><img class="w-10" src="~/assets/img/instagram.png" alt=""></a>
               </div>
             </div>

             <div class="min-w-max">
                <p class="text-center">@2022 Copyright All Right Reserved by Bengal Shop</p>
             </div>

             <div class="w-48">
                  <a href=""><img src="~/assets/img/payment.png" alt=""></a>
             </div>
        </div>
      </div>

    </div>


       <!-- product details model -->

       <div v-if="modal" class="fixed w-full h-full min-h-screen z-30 top-0 left-0">
           <div @click.prevent="modalClose" class="absolute h-full w-full bg-black opacity-60 top-0 left-0"></div>
           <div class="bg-model-body bg-white rounded-2xl p-8 relative z-30 mx-auto my-10">
            <svg @click.prevent="modalClose" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 absolute top-5 right-5 cursor-pointer">
              <path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
            </svg>

                  <div class="flex -mx-8">
                    <div class="w-1/2 px-8">
                      <img class="rounded-xs" :src="product.image" alt="">
                    </div>
                    <div class="w-1/2">
                       <div class="min-w-max w-60">
                        <div class="flex text-base">
                          <h5 class="text-gray-200 mr-8">Status</h5>
                          <h5 class="text-green-500">In Stock</h5>
                       </div>
                       <h2 class="text-2xl font-medium w-full mt-3">{{product.name}}</h2>
                        <div class="flex mt-3 items-center">
                          <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-4 h-4 text-yellow-500">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M11.48 3.499a.562.562 0 011.04 0l2.125 5.111a.563.563 0 00.475.345l5.518.442c.499.04.701.663.321.988l-4.204 3.602a.563.563 0 00-.182.557l1.285 5.385a.562.562 0 01-.84.61l-4.725-2.885a.563.563 0 00-.586 0L6.982 20.54a.562.562 0 01-.84-.61l1.285-5.386a.562.562 0 00-.182-.557l-4.204-3.602a.563.563 0 01.321-.988l5.518-.442a.563.563 0 00.475-.345L11.48 3.5z" />
                          </svg>
                          <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-4 h-4 text-yellow-500">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M11.48 3.499a.562.562 0 011.04 0l2.125 5.111a.563.563 0 00.475.345l5.518.442c.499.04.701.663.321.988l-4.204 3.602a.563.563 0 00-.182.557l1.285 5.385a.562.562 0 01-.84.61l-4.725-2.885a.563.563 0 00-.586 0L6.982 20.54a.562.562 0 01-.84-.61l1.285-5.386a.562.562 0 00-.182-.557l-4.204-3.602a.563.563 0 01.321-.988l5.518-.442a.563.563 0 00.475-.345L11.48 3.5z" />
                          </svg>
                          <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-4 h-4 text-yellow-500">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M11.48 3.499a.562.562 0 011.04 0l2.125 5.111a.563.563 0 00.475.345l5.518.442c.499.04.701.663.321.988l-4.204 3.602a.563.563 0 00-.182.557l1.285 5.385a.562.562 0 01-.84.61l-4.725-2.885a.563.563 0 00-.586 0L6.982 20.54a.562.562 0 01-.84-.61l1.285-5.386a.562.562 0 00-.182-.557l-4.204-3.602a.563.563 0 01.321-.988l5.518-.442a.563.563 0 00.475-.345L11.48 3.5z" />
                          </svg>
                          <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-4 h-4 text-yellow-500">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M11.48 3.499a.562.562 0 011.04 0l2.125 5.111a.563.563 0 00.475.345l5.518.442c.499.04.701.663.321.988l-4.204 3.602a.563.563 0 00-.182.557l1.285 5.385a.562.562 0 01-.84.61l-4.725-2.885a.563.563 0 00-.586 0L6.982 20.54a.562.562 0 01-.84-.61l1.285-5.386a.562.562 0 00-.182-.557l-4.204-3.602a.563.563 0 01.321-.988l5.518-.442a.563.563 0 00.475-.345L11.48 3.5z" />
                          </svg>
                          <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-4 h-4 text-yellow-500">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M11.48 3.499a.562.562 0 011.04 0l2.125 5.111a.563.563 0 00.475.345l5.518.442c.499.04.701.663.321.988l-4.204 3.602a.563.563 0 00-.182.557l1.285 5.385a.562.562 0 01-.84.61l-4.725-2.885a.563.563 0 00-.586 0L6.982 20.54a.562.562 0 01-.84-.61l1.285-5.386a.562.562 0 00-.182-.557l-4.204-3.602a.563.563 0 01.321-.988l5.518-.442a.563.563 0 00.475-.345L11.48 3.5z" />
                          </svg>

                          <h3 class="font-medium text-base text-gray-400 ml-2 text-center">10 reviews</h3>

                        </div>

                         <div class="flex mt-3 items-center">
                             <span class="text-3xl font-medium">${{product.sale}}</span><del class="mx-2 text-xl">${{product.price}}</del>
                             <h3 class="text-sm">(+15% Vat Included)</h3>
                         </div>

                         <div style="height:1px;" class="w-full mt-3 bg-gray-100"></div>
                          <div class="flex items-center  mt-3 text-2xl ">
                            <h4 class="text-base mr-4 font-medium">Quantity</h4>
                            <button class="w-10 h-10 border text-black border-gray-300 rounded-full">-</button>
                            <span class="mx-3 w-10 h-10 text-xl text-black bg-gray-300 rounded-full flex justify-center items-center">1</span>
                            <button class="w-10 h-10 border text-black border-gray-300 rounded-full">-</button>
                            <h3 class="text-sm ml-4">Only !0 Item Left!</h3>
                          </div>


                          <button class="bg-green-500 text-white w-full mt-3  rounded-full py-3 px-10">Add to Cart</button>


                          <div class="flex justify-between mt-3 text-sm">
                              <h4 class="flex items-center">
                                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-4 h-4 mr-1">
                                  <path stroke-linecap="round" stroke-linejoin="round" d="M21 8.25c0-2.485-2.099-4.5-4.688-4.5-1.935 0-3.597 1.126-4.312 2.733-.715-1.607-2.377-2.733-4.313-2.733C5.1 3.75 3 5.765 3 8.25c0 7.22 9 12 9 12s9-4.78 9-12z" />
                                </svg>
                                Add to Wishlist
                              </h4>

                              <h4 class="flex items-center">
                                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-4 h-4 mr-1">
                                  <path stroke-linecap="round" stroke-linejoin="round" d="M7.217 10.907a2.25 2.25 0 100 2.186m0-2.186c.18.324.283.696.283 1.093s-.103.77-.283 1.093m0-2.186l9.566-5.314m-9.566 7.5l9.566 5.314m0 0a2.25 2.25 0 103.935 2.186 2.25 2.25 0 00-3.935-2.186zm0-12.814a2.25 2.25 0 103.933-2.185 2.25 2.25 0 00-3.933 2.185z" />
                                </svg>
                                Share
                              </h4>
                          </div>

                          <div style="height:1px;" class="w-full mt-3 bg-gray-100"></div>


                          <div class="text-sm mt-5">
                            <p>Category :

                              <span v-for="(item,index) in product.categories" :key="index"><nuxt-link class="text-green-500" :to="'category/'+ item.name">{{ item.name }} </nuxt-link><span class="comma">, </span></span>
                            </p>
                            <p>Tag :

                              <span v-for="(item,index) in product.tags" :key="index"><nuxt-link class="text-green-500" :to="'tag/'+ item.name">{{ item.name }} </nuxt-link><span class="comma">, </span></span>
                              </p>
                          </div>

                       </div>
                    </div>
                  </div>
               </div>
          </div>
        </div>
</template>

<script>
import Logo from './logo.vue';
export default {
    data() {
      return {
         modal : false,
         product: ''
      }
    },

    methods: {
      modalClose(){
         this.$store.dispatch("product_details_modal/resetModal")
      }
    },

    mounted() {
    this.$store.watch(
      () => {
        return this.$store.getters["product_details_modal/getModal"]
      },
      (val)=>{
        this.modal = val.modal
        this.product = val.product
      },
      {
        deep:true
      }
    );
  },

  components: { Logo }
}
</script>
