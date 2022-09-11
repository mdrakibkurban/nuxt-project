<template>
  <div class="container mx-auto py-6">
      <div class="flex">
         <div class="w-1/4 pr-6">
            <Sidebar/>
         </div>
         <div class="w-3/4">
             <div class="h-60 bg-gray-50 mb-6">
                 <div class="h-full w-full flex justify-center items-center">
                    <img class="h-full" src="~/assets/img/hero.png" alt="">
                    <div class="absolute w-96 category-slide">
                       <h5 class="text-red-400 text-xl mb-3">Buy 1 Get 1</h5>
                       <h3 class="text-4xl text-green-600">Up to 30% Discount on Selected Items</h3>
                    </div>
                 </div>
             </div>
                <div class="flex justify-between items-center mb-8">
                  <h3 class="text-3xl">Category heading</h3>
                  <div class="min-w-max flex items-center">
                    <div class="text-sm mr-6"><b>20</b> Products Found</div>
                    <select name="" id="">
                      <option value="">Default sorting</option>
                      <option value="">Sort by price</option>
                      <option value="">Sort by discount</option>
                    </select>
                  </div>
               </div>


               <div class="flex flex-wrap -mx-4">
                <div v-for="item in 12" :key="item" class="w-1/3 px-4 mb-10">
                  <SingleProduct :product="item"/>
                </div>
              </div>
        </div>
      </div>
    </div>


</template>

<script>
  import Sidebar from "../components/Sidebar";
  import SingleProduct from "../components/SingleProduct";
export default {
  components: {SingleProduct, Sidebar}
}
</script>
