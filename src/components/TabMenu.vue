<template>
  <div id="TabMenu" class="bg-gray-100">
    <div class="my-3 sm:my-10 flex flex-wrap justify-center sm:justify-between text-center px-5 sm:px-24 space-x-4 ml-auto bg-gray-100">
      <h1 class="text-gray-800 text-xl mt-5 sm:text-3xl font-bold">Semua Makanan Kami</h1>
      <div class="btn flex gap-5">
        <div
          v-for="(tab, index) in tabs"
          :key="index"
          @click="changeTab(index)"
          :class="{ ' text-white bg-emerald-600': activeTab === index, 'cursor-pointer': activeTab !== index }"
          class="p-2 w-20 mt-5 mb-5 rounded-lg bg-emerald-600"
        >
          {{ tab.label }}
        </div>
      </div>
    </div>

    <!-- Display the content of the active tab -->
    <div class="mt-4 bg-gray-100 flex flex-wrap justify-center gap-9">
      <slot :tab="tabs[activeTab]">
        <div v-for="(card, cardIndex) in tabs[activeTab].cards" :key="cardIndex" class="flex justify-center gap-5">
          <div class="bg-white text-slate-800 p-4 rounded mb-4 w-[350px] h-[460px]">
            <img :src="card.image" :alt="'Image ' + (cardIndex + 1)" class="w-full h-52 object-cover mb-2 rounded">
            <div class="title flex justify-between my-3">
              <h3 class="text-lg font-semibold">{{ card.title }}</h3>
              <p class="text-sm font-semibold text-yellow-300">{{ card.price }}</p>
            </div>
            <p class="overflow-y-auto max-h-28">{{ card.description }}</p>
            <div class="btn bg-emerald-600 mt-4 rounded-lg w-fit p-2 text-white hover:bg-emerald-700 flex gap-3 items-center">
              <a href="">Masukkan Keranjang</a>
              <img width="25" height="25" src="https://img.icons8.com/ios-glyphs/30/FFFFFF/plus--v1.png" alt="plus--v1"/>
            </div>  
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
        {
          label: 'Betawi',
          cards: [
            {
              title: 'Card 1',
              image: 'https://images.unsplash.com/photo-1572656631137-7935297eff55?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D',
              description: 'Lorem, ipsum dolor sit amet consectetur adipisicing elit. Voluptas eligendi mollitia et, aperiam ex sunt cupiditate fugit reiciendis beatae nostrum exercitationem suscipit similique repellendus labore. Quas recusandae deleniti qui impedit.',
              price: 'Rp. 25.000,00',
            },
            {
              title: 'Card 1',
              image: 'https://images.unsplash.com/photo-1526619971180-973e2a5045fb?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA==',
              description: 'Lorem, ipsum dolor sit amet consectetur adipisicing elit. Voluptas eligendi mollitia et, aperiam ex sunt cupiditate fugit reiciendis beatae nostrum exercitationem suscipit similique repellendus labore. Quas recusandae deleniti qui impedit.',
              price: 'Rp. 25.000,00',
            },
            {
              title: 'Card 1',
              image: 'https://images.unsplash.com/photo-1681378128359-a5c2492a3535?q=80&w=1974&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA==',
              description: 'Lorem, ipsum dolor sit amet consectetur adipisicing elit. Voluptas eligendi mollitia et, aperiam ex sunt cupiditate fugit reiciendis beatae nostrum exercitationem suscipit similique repellendus labore. Quas recusandae deleniti qui impedit.',
              price: 'Rp. 25.000,00',
            },
            {
              title: 'Card 1',
              image: 'https://images.unsplash.com/photo-1504674900247-0877df9cc836?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA==',
              description: 'Lorem, ipsum dolor sit amet consectetur adipisicing elit. Voluptas eligendi mollitia et, aperiam ex sunt cupiditate fugit reiciendis beatae nostrum exercitationem suscipit similique repellendus labore. Quas recusandae deleniti qui impedit.',
              price: 'Rp. 25.000,00',
            },
            {
              title: 'Card 1',
              image: 'https://images.unsplash.com/photo-1512621776951-a57141f2eefd?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA==',
              description: 'Lorem, ipsum dolor sit amet consectetur adipisicing elit. Voluptas eligendi mollitia et, aperiam ex sunt cupiditate fugit reiciendis beatae nostrum exercitationem suscipit similique repellendus labore. Quas recusandae deleniti qui impedit.',
              price: 'Rp. 25.000,00',
            },
            {
              title: 'Card 1',
              image: 'https://images.unsplash.com/photo-1490474418585-ba9bad8fd0ea?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA==',
              description: 'Lorem, ipsum dolor sit amet consectetur adipisicing elit. Voluptas eligendi mollitia et, aperiam ex sunt cupiditate fugit reiciendis beatae nostrum exercitationem suscipit similique repellendus labore. Quas recusandae deleniti qui impedit.',
              price: 'Rp. 25.000,00',
            },
            // Add more cards as needed
          ],
        },
        {
          label: 'Jawa',
          cards: [
            {
              title: 'Card 1',
              image: 'https://images.unsplash.com/photo-1464305795204-6f5bbfc7fb81?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA==',
              description: 'Lorem, ipsum dolor sit amet consectetur adipisicing elit. Voluptas eligendi mollitia et, aperiam ex sunt cupiditate fugit reiciendis beatae nostrum exercitationem suscipit similique repellendus labore. Quas recusandae deleniti qui impedit.',
              price: 'Rp. 25.000,00',
            },
            {
              title: 'Card 1',
              image: 'https://images.unsplash.com/photo-1591814468924-caf88d1232e1?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA==',
              description: 'Lorem, ipsum dolor sit amet consectetur adipisicing elit. Voluptas eligendi mollitia et, aperiam ex sunt cupiditate fugit reiciendis beatae nostrum exercitationem suscipit similique repellendus labore. Quas recusandae deleniti qui impedit.',
              price: 'Rp. 25.000,00',
            },
            {
              title: 'Card 1',
              image: 'https://images.unsplash.com/photo-1555232967-d2c10a468149?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA==',
              description: 'Lorem, ipsum dolor sit amet consectetur adipisicing elit. Voluptas eligendi mollitia et, aperiam ex sunt cupiditate fugit reiciendis beatae nostrum exercitationem suscipit similique repellendus labore. Quas recusandae deleniti qui impedit.',
              price: 'Rp. 25.000,00',
            },
            // Add more cards as needed
          ],
        },
        {
          label: 'Bali',
          cards: [
            {
              title: 'Card 1',
              image: 'https://images.unsplash.com/photo-1664337873053-840ea51d271d?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA==',
              description: 'Lorem, ipsum dolor sit amet consectetur adipisicing elit. Voluptas eligendi mollitia et, aperiam ex sunt cupiditate fugit reiciendis beatae nostrum exercitationem suscipit similique repellendus labore. Quas recusandae deleniti qui impedit.',
              price: 'Rp. 25.000,00',
            },
            {
              title: 'Card 1',
              image: 'https://images.unsplash.com/photo-1572656631137-7935297eff55?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D',
              description: 'Lorem, ipsum dolor sit amet consectetur adipisicing elit. Voluptas eligendi mollitia et, aperiam ex sunt cupiditate fugit reiciendis beatae nostrum exercitationem suscipit similique repellendus labore. Quas recusandae deleniti qui impedit.',
              price: 'Rp. 25.000,00',
            },
            {
              title: 'Card 1',
              image: 'https://images.unsplash.com/photo-1569562211093-4ed0d0758f12?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA==',
              description: 'Lorem, ipsum dolor sit amet consectetur adipisicing elit. Voluptas eligendi mollitia et, aperiam ex sunt cupiditate fugit reiciendis beatae nostrum exercitationem suscipit similique repellendus labore. Quas recusandae deleniti qui impedit.',
              price: 'Rp. 25.000,00',
            },
            {
              title: 'Card 1',
              image: 'https://images.unsplash.com/photo-1572656631137-7935297eff55?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D',
              description: 'Lorem, ipsum dolor sit amet consectetur adipisicing elit. Voluptas eligendi mollitia et, aperiam ex sunt cupiditate fugit reiciendis beatae nostrum exercitationem suscipit similique repellendus labore. Quas recusandae deleniti qui impedit.',
              price: 'Rp. 25.000,00',
            },
            // Add more cards as needed
          ],
        },
        // Repeat the structure for other tabs
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
