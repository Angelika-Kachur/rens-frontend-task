<template>
  <div class="home">
    <Promo></Promo>
    <section class="slider-section">
      <Logo></Logo>
      <Slider></Slider>
    </section>
  </div>
</template>

<script>
import Logo from "@/components/Logo.vue";
import Slider from "@/components/Slider.vue";
import Promo from "@/components/Promo.vue";

export default {
  name: "home",
  components: {
    Slider,
    Logo,
    Promo
  }
};
</script>

<style scoped>
.slider-section {
  position: relative;
}
</style>
