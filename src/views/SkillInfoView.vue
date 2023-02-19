<template>
  <div class="about">
    <h1>This is an about page</h1>
    <img alt="Vue logo" src="../assets/.png" />
  </div>
</template>


<template>
  <div class="skill_info">
    <a v-for="(menu, key) in menus" :key="key">{{menu}}</a>
  </div>

  <div v-for="(product, key) in products" :key="key">
    <img class="room-img" :src="product.imgSrc" alt="image" />
    <h4>{{product.name}}</h4>
    <p>{{product.price}}</p>
    <button @click="reportFakeProduct(key)">허위매물신고</button> <span>신고수 : {{product.fakeReport}}</span>
  </div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      menus: ['Home', 'Shop', 'About'],
      products : [
        {name: '역삼동 원룸', price: '70만원', fakeReport: 0, imgSrc: require('./assets/images/room0.jpg')},
        {name: '천호동 원룸', price: '50만원', fakeReport: 0, imgSrc: require('./assets/images/room1.jpg')},
        {name: '마포구 원룸', price: '60만원', fakeReport: 0, imgSrc: require('./assets/images/room2.jpg')},
      ]
    }
  },
  methods: {
    reportFakeProduct(num) {
      this.products[num].fakeReport = this.products[num].fakeReport + 1;
    }
  },  
}
</script>