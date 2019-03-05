<template>
  <div class="slider">
    <div
      class="slide"
      :class="{ active: slideActive === index }"
      v-for="(slide, index) in slides"
      :key="slide.id"
      :style="{ 'background-image': 'url(' + slide.url + ')' }"
    >
      <h2 class="slider-text">
        {{ slide.sliderText }}
      </h2>
    </div>

    <div class="controls">
      <span
        class="dot"
        :class="{ active: slideActive === index }"
        v-for="(slide, index) in slides"
        :key="slide.id"
        @click="activateSlide(index)"
      ></span>
    </div>
  </div>
</template>

<script>
import slidesJson from "../data/slides.json";

export default {
  name: "slider",
  data() {
    return {
      slideActive: 0,
      slideInterval: null,
      slides: slidesJson
    };
  },
  methods: {
    activateSlide: function(index) {
      this.slideActive = index;
      this.restartInterval();
    },
    nextSlide: function() {
      this.slideActive = (this.slideActive + 1) % this.slides.length;
    },
    startInterval: function() {
      return setInterval(this.nextSlide, 5000);
    },
    restartInterval: function() {
      clearInterval(this.slideInterval);
      this.slideInterval = this.startInterval();
    }
  },
  created() {
    this.slideInterval = this.startInterval();
  }
};
</script>

<style scoped>
.slider {
  position: relative;
}
.slide {
  display: none;
  align-items: center;
  justify-content: center;
  transition: ease all 0.2s;
  background-size: cover;
  background-position: 50% 70%;
  text-align: center;
  padding: 200px 20px;
  height: calc(100vh - 60px);
}
.slide.active {
  display: flex;
}
.slide:nth-child(2) {
  justify-content: start;
}
.slide:nth-child(2) .slider-text {
  padding: 0 7%;
}
.slider-text {
  color: #fff;
  font-size: 50px;
  margin: 0;
  padding: 0;
}
.controls {
  position: absolute;
  top: 50%;
  right: 10px;
  transform: translateY(-50%);
}
.dot {
  display: block;
  width: 8px;
  height: 8px;
  background: transparent;
  border: solid 1px #fff;
  border-radius: 100%;
  margin: 7px 0;
  cursor: pointer;
  position: relative;
  transition: all ease 0.3s;
}
.dot:after {
  content: "";
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 20px;
  height: 16px;
}
.dot.active {
  background: #fff;
}

@media only screen and (max-width: 768px) {
  .slide {
    padding: 50px 10px;
    height: calc(100vh - 65px);
  }
  .slider-text {
    font-size: 34px;
  }
}
</style>
