<template>
  <div class="container mx-auto py-20">
    <h3 class="text-center font-medium text-2xl mb-4">Cart Item</h3>
      <table class="table-auto w-full">
         <thead>
          <tr>
            <th style="width:50px;" class="border px-4 py-2">Remove</th>
            <th style="width:50px;" class="border px-4 py-2">Image</th>
            <th class="border px-4 py-2">Name</th>
            <th class="border px-4 py-2">Price</th>
            <th class="border px-4 py-2">Quantity</th>
            <th class="border px-4 py-2">Total</th>

         </tr>
         </thead>

         <tbody>
            <tr v-for="product in products" :key="product.id">
              <td class="border px-4 py-2 text-center">

                <button @click.prevent="removeCart(product.id)">
                  <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
                  <path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
                 </svg>
                </button>

              </td>
              <td class="border px-4 py-2 text-center"><img width="50" :src="product.image" alt=""></td>
              <td class="border px-4 py-2 text-center">{{ product.name }}</td>
              <td class="border px-4 py-2 text-center">${{ product.price.toFixed(2) }}</td>
              <td class="border px-4 py-2 text-center">
                <div class="flex justify-center">
                  <button class="h-6 w-6 bg-gray-50 rounded-full mr-3 font-bold" @click.prevent="cartChange(product,'minus')">-</button>
                    {{ product.quantity }}
                  <button class="h-6 w-6 bg-gray-50 rounded-full ml-3 font-bold" @click.prevent="cartChange(product,'plus')">+</button>
                </div>
              </td>
              <td class="border px-4 py-2 text-center">${{ (product.price * product.quantity).toFixed(2) }}</td>

            </tr>

            <tr>
              <td colspan="5" class="border px-4 py-2 text-center">Grandtotal</td>
              <td  class="border px-4 py-2 text-center">${{ total.toFixed(2) }}</td>
            </tr>
         </tbody>
      </table>
  </div>
</template>

<script>
export default {
   data() {
    return {
        products : [],
        total : 0
    }
   },

   methods:{

    removeCart(product_id){
        this.$store.dispatch('cart/removeCart', product_id)
        this.getCart();
    },

    cartChange(product, type) {
         this.$store.dispatch("cart/addToCart",
          {
            product: product,
            type: type
          }
        );

        this.getCart();
    },

     getCart(){
          const getProductsLocalStorage = JSON.parse(localStorage.getItem('cart'));
          const getProductsStore = this.$store.getters["cart/getCart"];

          if(getProductsStore.length) {
            this.products = getProductsStore;
          } else {
            this.products = getProductsLocalStorage;
          }

          this.products.forEach(item =>{
             this.total += (item.quantity * item.price);
          })
     }
   },
   mounted(){
     this.getCart();
   }
}
</script>
