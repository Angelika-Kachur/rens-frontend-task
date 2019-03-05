<template>
  <div class="holder">
    <div class="product">
      <div class="image">
        <img src="assets/product_image.png" alt="Rens White">
      </div>
      <div class="text">
        <a href="#" class="title" title="Rens White">Rens White</a>
        <div class="price">99$</div>
      </div>
      <button class="buy-btn">Buy now</button>
    </div>
  </div>
</template>


<style scoped>
.product {
  border: 1px solid black;
  padding: 15px;
  box-shadow: -5px 8px 5px 2px #cecece;
  transition: transform ease 0.3s;
}
.product:hover {
  transform: scale(1.1);
}
.product .image {
  margin: 0 0 10px;
}
.product .title {
  font-size: 20px;
  margin: 0 0 10px;
  display: block;
}
.product a {
  color: #000;
  text-decoration: none;
  transition: all ease 0.3s;
}
.product a:hover {
  color: #f25f5c;
}
.product .price {
  font-size: 16px;
  margin: 0 0 10px;
}
.product .buy-btn {
  width: 100%;
  background: #f25f5c;
  color: white;
  outline: none;
  padding: 10px;
  cursor: pointer;
  border: 1px solid transparent;
  transition: all ease 0.3s;
}
.product .buy-btn:hover {
  background: #c54947;
  border-color: #c54947;
}
</style>
