<template>

  <div class="single-bs-product">
                <div class="h-80 relative  mb-4">
                  <div class="bg-gray-50 h-full flex justify-center items-center p-4">
                    <img :src="product.image" alt="">
                  </div>

                  <div class="single-bs-product-hover absolute top-0 left-0 w-full h-full flex justify-center items-center">
                      <div class="bg-black absolute w-full h-full opacity-60"></div>

                      <button @click.prevent="productDetails" class="absolute left-0 bottom-0 bg-gray-200 w-full p-2 flex justify-center items-center">Details
                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-5 h-5 ml-2">
                          <path stroke-linecap="round" stroke-linejoin="round" d="M17.25 8.25L21 12m0 0l-3.75 3.75M21 12H3" />
                        </svg>
                      </button>

                      <div v-if="!matched" class="relative z-10">
                         <button @click.prevent="addToCart(product,'plus')" class="text-white text-2xl cursor-pointer">Add to Bag</button>
                      </div>

                       <div v-if="matched" class="relative z-10">
                           <div class="flex justify-center items-center mb-6 text-4xl text-white">
                            <button @click.prevent="addToCart(product,'minus')" class="w-12 h-12 border border-white rounded-full">-</button>
                            <span class="mx-3 w-12 h-12 text-2xl text-green-500 bg-white rounded-full flex justify-center items-center">{{ quantity }}</span>
                            <button @click.prevent="addToCart(product,'plus')"  class="w-12 h-12 border border-white rounded-full">+</button>
                           </div>
                       </div>

                  </div>

                </div>
                <div class="text-center">
                  <h4 class="text-xl mb-3 font-medium">{{product.name}}</h4>
                  <p><span class="font-medium text-lg">${{product.sale}}</span> <del class="text-gray-400">${{product.price}}</del></p>
                </div>
            </div>
</template>


<script>
export default {
    props:['product'],
    data() {
      return {
        matched: false,
        quantity: ''
      }
    },

    methods: {
       productDetails(){
           this.$store.dispatch('product_details_modal/triggerModal',this.product);
       },

       addToCart(product, type) {
          this.$store.dispatch("cart/addToCart",
            {
              product: product,
              type: type
            }
          );
        },
        productChecker(){
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
                  if(item.id === this.product.id) {
                      this.matched = true;
                      this.quantity = item.quantity
                  }
                })
            }
        }
    },

    mounted(){

        this.productChecker();

        this.$store.watch(
        () => {
          return this.$store.getters["cart/getCart"]
        },
        (val) => {
          this.productChecker();

        },
        {
          deep:true
        }
      );


    }


}
</script>
