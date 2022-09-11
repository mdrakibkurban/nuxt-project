<template>
  <div>
      <div class="container mx-auto">
         <div class="py-6 flex justify-between items-center">

          <Logo/>

          <div class="w-96">
             <div class="border border-gray-100 p-1 flex rounded-full items-center">
                <div class="min-w-max">
                   <img class="px-3" src="~assets/img/search.png" alt="">
                </div>
                <input class="w-full px-3 pxy-1 focus:outline-none" type="search" placeholder="search here..">
                <button type="submit" class="bg-gray bg-btn-gray px-6 py-2 rounded-full text-white">Search</button>
             </div>
          </div>

          <div class="min-w-max flex items-center">
                <nuxt-link to="">
                 <span class="bs-icon-box rounded-full hover:bg-gray-200  flex items-center justify-center"> <img src="~assets/img/heart.png" alt=""></span>
                </nuxt-link>
                <nuxt-link to="/cart" class="relative mx-4">
                  <span class="bs-icon-box rounded-full hover:bg-gray-200  flex items-center justify-center"> <img src="~assets/img/Vector.png" alt=""></span>
                  <span class="absolute bg-red-600 w-4 h-4 top-0 right-0 rounded-full text-xs text-white flex justify-center items-center">{{count}}</span>
                </nuxt-link>
                <nuxt-link to="/" class="flex items-center">
                  <span class="bs-icon-box rounded-full hover:bg-gray-200  flex items-center justify-center"><img src="~assets/img/user.png" alt=""></span>
                  <span>Account</span>
                </nuxt-link>
          </div>
         </div>


          <div class="flex items-center">
             <div v-click-outside="menuClose" class="w-96 relative">
                 <div @click.prevent="menuClick" class="flex rounded-full relative z-20 bg-green-500 px-4 py-2 items-center cursor-pointer">
                     <div class="min-w-max">
                         <img class="px-3" src="~assets/img/menu-right.png" alt="">
                     </div>
                     <div class="w-full text-center px-4 text-white">
                           All Categories
                     </div>
                     <div class="min-w-max">
                        <img class="px-3" src="~assets/img/chevron-down.png" alt="">
                     </div>
                 </div>

                  <div v-bind:class = "allCategoryMenu ? 'visible block' : 'invisible hidden'" class="absolute bg-green-500 w-full z-10 -mt-5 pt-6 pb-4 rounded-b-2xl">
                       <ul>
                        <li><nuxt-link class="text-white py-2 px-4 block hover:text-black" to="">Fruits</nuxt-link></li>
                        <li><nuxt-link class="text-white py-2 px-4 block hover:text-black" to="">vegetables</nuxt-link></li>
                        <li><nuxt-link class="text-white py-2 px-4 block hover:text-black" to="">vegetables</nuxt-link></li>
                        <li><nuxt-link class="text-white py-2 px-4 block hover:text-black" to="">Fruits</nuxt-link></li>
                        <li><nuxt-link class="text-white py-2 px-4 block hover:text-black" to="">vegetables</nuxt-link></li>
                        <li><nuxt-link class="text-white py-2 px-4 block hover:text-black" to="">Fruits</nuxt-link></li>
                      </ul>
                 </div>

             </div>

             <div class="w-full">
                    <ul class="flex justify-center">
                       <li><nuxt-link class="p-4" to="/">Home</nuxt-link></li>
                       <li><nuxt-link class="p-4" to="/category">Category</nuxt-link></li>
                       <li><nuxt-link class="p-4" to="/">Page</nuxt-link></li>
                       <li><nuxt-link class="p-4" to="/">Blog</nuxt-link></li>
                        <li><nuxt-link class="p-4" to="/">Contact</nuxt-link></li>
                       <li><nuxt-link class="p-4" to="/">Track Offer</nuxt-link></li>
                    </ul>
              </div>
             <nuxt-link to="/" class="min-w-max flex">
                    <img class="mr-3" src="~assets/img/u_percentage.png" alt="">Special Offers!
             </nuxt-link>
          </div>
      </div>
  </div>
</template>

<script>
import Logo from './logo.vue';
export default {
    components: { Logo },
    data() {
      return {
         allCategoryMenu : false,
         count : 0
      }
    },

    methods: {
       menuClick(){
           this.allCategoryMenu = !this.allCategoryMenu
       },

       menuClose(){
         this.allCategoryMenu = false
       },

       cartChecker(){
          const getProductsLocalStorage = JSON.parse(localStorage.getItem('cart'));
          const getProductsStore = this.$store.getters["cart/getCart"];

          let cart = [];
          if(getProductsStore.length) {
            cart = getProductsStore;
          } else {
            cart = getProductsLocalStorage;
          }

          if(cart.length){
              cart.forEach(item => {
                 this.count = (this.count + item.quantity);
              })
          }
       }
    },

    mounted(){
      let getProductsLocalStorage = JSON.parse(localStorage.getItem('cart'));

        if(getProductsLocalStorage === null){
          localStorage.setItem('cart', '[]');
        }


        this.cartChecker();

        this.$store.watch(
        () => {
          return this.$store.getters["cart/getCart"]
        },
        (val) => {
          this.cartChecker();

        },
        {
          deep:true
        }
        );

    }


}
</script>
