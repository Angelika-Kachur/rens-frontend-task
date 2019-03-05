<template>
  <div class="promo">
    <div class="text">
      Get EXCLUSIVE early-bird deal: 99$ <span class="old-price">$140</span>
      <span class="additional">by subscribing tp our email list</span>
    </div>
    <router-link class="rens-shop" to="/shop">Rens Shop</router-link>
  </div>
</template>

<style scoped>
.promo {
  padding: 20px 40px;
  background: #f25f5c;
  color: #fff;
  position: relative;
}
.old-price {
  text-decoration: line-through;
}
.rens-shop {
  position: absolute;
  top: 50%;
  right: 20px;
  transform: translateY(-50%);
  color: #fff;
  font-weight: bold;
  z-index: 2;
  text-decoration: none;
  transition: all ease 0.3s;
}
.rens-shop:hover {
  transform: translateY(-50%) scale(1.2);
}

@media only screen and (max-width: 768px) {
  .promo {
    padding: 10px;
  }
  .promo .text {
    margin: 0 0 5px;
  }
  .rens-shop {
    position: static;
  }
  .promo .additional {
    display: none;
  }
}
</style>
