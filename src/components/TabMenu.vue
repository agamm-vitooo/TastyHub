<template>
  <div>
    <div class="my-3 sm:my-10 flex px-5 sm:px-24 space-x-4 ml-auto bg-gray-100">
      <h1 class="text-gray-800 text-xl sm:text-3xl font-bold">Semua Makanan Kami</h1>
      <div class="btn flex">
  <!-- Loop through tabs and display them -->
      <div
        v-for="(tab, index) in tabs"
        :key="index"
        @click="changeTab(index)"
        :class="{ ' text-white bg-emerald-600 active:bg-emerald-600': activeTab === index, 'cursor-pointer': activeTab !== index }"
        class="px-4 py-2 rounded"
      >
        {{ tab.label }}
      </div>
    </div>
    </div>


    <!-- Display the content of the active tab -->
    <div class="mt-4 bg-gray-100">
      <slot :tab="tabs[activeTab]">
        <!-- Content for Tab 1 -->
        <div v-if="activeTab === 0" class="flex flex-wrap justify-center gap-5">
          <div class="bg-white text-slate-800 p-4 rounded mb-4 w-[350px] h-[460px]">
            <img src="https://images.unsplash.com/photo-1572656631137-7935297eff55?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" alt="Image 1" class="w-full h-52 object-cover mb-2 rounded">
            <div class="title flex justify-between my-3">
              <h3 class="text-lg font-semibold">Card 1</h3>
              <p class="text-sm font-semibold text-yellow-300">Rp. 25.000,00</p>
            </div>
            <p class="overflow-y-auto max-h-28">Lorem, ipsum dolor sit amet consectetur adipisicing elit. Voluptas eligendi mollitia et, aperiam ex sunt cupiditate fugit reiciendis beatae nostrum exercitationem suscipit similique repellendus labore. Quas recusandae deleniti qui impedit.</p>
            <div class="btn bg-emerald-600 mt-4 rounded-lg w-fit p-2 text-white hover:bg-emerald-700 flex gap-3 items-center">
              <a href="">Masukan Keranjang</a>
              <img width="30" height="30" src="https://img.icons8.com/ios-glyphs/30/FFFFFF/plus--v1.png" alt="plus--v1"/>
            </div>  
          </div>
          <div class="bg-white text-slate-800 p-4 rounded mb-4 w-[350px] h-[460px]">
            <img src="https://images.unsplash.com/photo-1526619971180-973e2a5045fb?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" alt="Image 2" class="w-full h-52 object-cover mb-2 rounded">
            <div class="title flex justify-between my-3">
              <h3 class="text-lg font-semibold">Card 2</h3>
              <p class="text-sm font-semibold text-yellow-300">Rp. 30.000,00</p>
            </div>
            <p class="overflow-y-auto max-h-28">Lorem ipsum dolor sit amet consectetur adipisicing elit. Excepturi pariatur eius eos vero deserunt cum eaque dolorem modi architecto nesciunt suscipit, ratione, odit eum recusandae a? Culpa ex recusandae dolore.</p>
                        <div class="btn bg-emerald-600 mt-4 rounded-lg w-fit p-2 text-white hover:bg-emerald-700 flex gap-3 items-center">
              <a href="">Masukan Keranjang</a>
              <img width="30" height="30" src="https://img.icons8.com/ios-glyphs/30/FFFFFF/plus--v1.png" alt="plus--v1"/>
            </div> 
          </div>
          <div class="bg-white text-slate-800 p-4 rounded w-[350px] h-[460px]">
            <img src="https://images.unsplash.com/photo-1681378128359-a5c2492a3535?q=80&w=1974&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" alt="Image 3" class="w-full h-52 object-cover mb-2 rounded">
            <div class="title flex justify-between my-3">
              <h3 class="text-lg font-semibold">Card 3</h3>
              <p class="text-sm font-semibold text-yellow-300">Rp. 20.000,00</p>
            </div>
            <p class="overflow-y-auto max-h-28">Lorem ipsum dolor sit amet consectetur adipisicing elit. Illum eligendi laudantium laboriosam eveniet, a inventore velit minus aperiam veniam perspiciatis possimus, optio porro, dolorem quos. Veritatis quasi ratione laborum reiciendis.</p>
                        <div class="btn bg-emerald-600 mt-4 rounded-lg w-fit p-2 text-white hover:bg-emerald-700 flex gap-3 items-center">
              <a href="">Masukan Keranjang</a>
              <img width="30" height="30" src="https://img.icons8.com/ios-glyphs/30/FFFFFF/plus--v1.png" alt="plus--v1"/>
            </div> 
          </div>
        </div>


        <!-- Content for Tab 2 -->
        <div v-if="activeTab === 1" class="flex justify-center gap-5">
          <div class="bg-yellow-100 text-slate-800 p-4 rounded mb-4 w-[200px] h-[200px]">
            <h3 class="text-lg font-semibold">{Card 1}</h3>
            <p>This is the content for Card 1 in Tab 2.</p>
          </div>
          <div class="bg-yellow-100 text-slate-800 p-4 rounded mb-4 w-[200px] h-[200px]">
            <h3 class="text-lg font-semibold">Card 2</h3>
            <p>This is the content for Card 2 in Tab 2.</p>
          </div>
          <div class="bg-yellow-100 text-slate-800 p-4 rounded w-[200px] h-[200px]">
            <h3 class="text-lg font-semibold">Card 3</h3>
            <p>This is the content for Card 3 in Tab 2.</p>
          </div>
        </div>

        <!-- Content for Tab 3 -->
        <div v-if="activeTab === 2" class="flex justify-center gap-5">
          <div class="bg-gray-200 text-slate-800 p-4 rounded mb-4 w-[200px] h-[200px]">
            <h3 class="text-lg font-semibold">Card 1</h3>
            <p>This is the content for Card 1 in Tab 3.</p>
          </div>
          <div class="bg-gray-200 text-slate-800 p-4 rounded mb-4 w-[200px] h-[200px]">
            <h3 class="text-lg font-semibold">Card 2</h3>
            <p>This is the content for Card 2 in Tab 3.</p>
          </div>
          <div class="bg-blue-100 text-slate-800 p-4 rounded w-[200px] h-[200px]">
            <h3 class="text-lg font-semibold">Card 3</h3>
            <p>This is the content for Card 3 in Tab 3.</p>
          </div>
        </div>
      </slot>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      tabs: [
        { label: 'Betawi', content: 'Content for Tab 1' },
        { label: 'Jawa', content: 'Content for Tab 2' },
        { label: 'Bali', content: 'Content for Tab 3' },
      ],
      activeTab: 0,
    };
  },
  methods: {
    changeTab(index) {
      this.activeTab = index;
    },
  },
};

</script>

<style scoped>
/* Add any custom styles here */
</style>
