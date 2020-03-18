<template>
  <div id="app">
    <Slider
      animation="fade"
      v-model="sliderValue"
      :duration="5000"
      :speed="1000"
    >
      <SliderItem
        v-for="image in products"
        :key="image"
      >
        <p style="line-height: 280px; font-size: 5rem; text-align: center;">
          <img v-bind:src="image.imageLink"/>
        </p>
      </SliderItem>
    </Slider>
  </div>
</template>

<script>
import { Slider, SliderItem } from "vue-easy-slider";

export default {
  name: "App",
  components: {
    Slider,
    SliderItem
  },
  data() {
    return {
      products:[{
       imageLink : require('@/assets/lap1.jpg'),
        name: "hp 15",
        price: "$ 200,000",
        specs: "1TB HDD, 16GB RAM",
        categoryId: 1

      },
      {
       id: 2,
          imageLink : require('@/assets/sli1.jpg'),
           
      },
       {
        id: 3,
          imageLink : require('@/assets/sli2.jpg'),
         
      },
       {
       id: 4,
          imageLink : require('@/assets/sli3.jpg'),
         
      },
       {
        id: 5,
          imageLink : require('@/assets/sli4.jpg'),
         
      },
      {
        id: 6,
          imageLink : require('@/assets/pb1.jpg'),
          
      }
      ],
      list: [],
      sliderValue: 2
    };
  },
  methods: {
    changeIndex(index) {
      this.sliderValue = index;
    }
  },
  mounted() {
    setTimeout(
      () =>
        (this.list = [
          {
            backgroundColor: "#3f51b5",
            width: "100%",
            height: "100%"
          },
          {
            backgroundColor: "#eee",
            width: "100%",
            height: "100%"
          },
          {
            backgroundColor: "#f44336",
            width: "100%",
            height: "100%"
          },
          {
            backgroundColor: "#eee",
            width: "100%",
            height: "100%"
          }
        ]),
      1000
    );
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 20px;
  margin-bottom: 10px;
  
  
}

p {
  margin: 0;
}
</style>
