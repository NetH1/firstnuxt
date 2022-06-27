<template>
  <div class="container mx-auto">
    <h1 class="text-2xl text-center mb-3 font-bold">
      Featured Categories
    </h1>
    <div class="flex flex-wrap justify-between">
      <div v-for="item of categories" :key="item.id" class="wid mb-4">
        <img class="w-full mb-2" :src="item.img" alt="">
        <p class="text-lg font-semibold">
          {{ item.name }}
        </p>
      </div>
    </div>
    <button class="bg-black text-white rounded-xl p-3 mx-auto block w-max mt-8" @click="sanzhar()">
      Open notification
    </button>
    <div class="state box-sh" :class="{ 'active' : setActive === 1 }">
      <h2 class="font-bold text-lg mb-3">
        Санжар верстать не умеет
      </h2>
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit.
        Id quasi numquam deserunt vitae dolor minus fugiat quia labore
        laudantium itaque voluptatem beatae esse magnam odit temporibus ab,
        aspernatur corporis rerum!
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'GameStop',
  data () {
    return {
      setActive: 0,
      categories: [
        { id: 1, name: 'Video Games', img: 'https://media.gamestop.com/i/gamestop/VGS_NewReleasesPokArceusEldenRing_336x336_4Up_D.webp' },
        { id: 2, name: 'Consoles', img: 'https://media.gamestop.com/i/gamestop/Homepage_FtrCategory_Consoles_264x264_5Up_D.webp' },
        { id: 3, name: 'Controllers', img: 'https://media.gamestop.com/i/gamestop/Homepage_FtrCategory_Controllers_264x264_5Up_D.webp' },
        { id: 4, name: 'PC Gaming', img: 'https://media.gamestop.com/i/gamestop/Homepage_FtrCategory_PCGaming_264x264_5Up_D.webp' },
        { id: 5, name: 'Electronics', img: 'https://media.gamestop.com/i/gamestop/Homepage_FtrCategory_Electronics_264x264_5Up_D.webp' },
        { id: 6, name: 'Keyboards', img: 'https://media.gamestop.com/i/gamestop/Homepage_FtrCategory_Keyboards_264x264_5Up_D.webp' },
        { id: 7, name: 'Headsets', img: 'https://media.gamestop.com/i/gamestop/Homepage_FtrCategory_Headsets_264x264_5Up_D.webp' },
        { id: 8, name: 'Collectibles', img: 'https://media.gamestop.com/i/gamestop/COLL_PO_StarWars_NightbrotherArcher_5Up_264x264_D.webp' },
        { id: 9, name: 'Toys & Games', img: 'https://media.gamestop.com/i/gamestop/Pokemon_Top_BtlAcademy_224x224_5Up_D.webp' },
        { id: 10, name: 'Clothing', img: 'https://media.gamestop.com/i/gamestop/DP_B1G1_RegPriceTs_286x286_4Up_D.webp' }
      ]
    }
  },
  methods: {
    sanzhar () {
      this.setActive = 1
      setTimeout(this.uhodSanzhara, 3000)
    },
    uhodSanzhara () {
      document.querySelector('.state').style.bottom = '-100%'
      document.querySelector('body').style.overflow = 'hidden'
      setTimeout(this.dis, 1000)
    },
    dis () {
      document.querySelector('body').style.overflowX = 'hidden'
      document.querySelector('body').style.overflowY = 'auto'
      document.querySelector('.state').style.bottom = '40px'
      this.setActive = 0
    }
  }
}
</script>
