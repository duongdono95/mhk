<template>
    <div class="product">
        <div class="image__container">
          <img class="img" :src="photoUrl" alt="product">
        </div>
        <p class="product__name">{{productName}}</p>
        <p class="price">${{price}}.00</p>
        <RouterLink :to="{name: 'details',params: {id:productData._id}}"><button class="product__button" type="post">See More -></button></RouterLink>
      </div>
</template>

<script>
    export default {
        props: {
          productData: Object
        },
        data () {
          return{
            _id: this.productData._id,
            photoUrl: this.productData.photoUrl,
            productName: this.productData.productName,
            sellerName: this.productData.sellerName, 
            price: this.productData.price
          }
        }
    }
</script>

<style scoped>
    .product {
  width: 400px;
  border: 2px solid #C51EED;
  border-radius: 10px;
  padding: 20px;
  display: flex;
  flex-direction: column;
  gap: 20px;
  margin: 0 auto 50px auto;
  box-shadow: 0 0  30px 10px rgba(225, 225, 225, 0.1) ;
}
.image__container {
  width: 100%;
  height: 350px;
}
.img {
  width: 100%;
  height: 100%;
  border-radius: 10px;
  object-fit: cover;

}
.product__name {
  color: rgba(255, 255, 255, 0.7);
  font-size: 24px;
  font-weight: 400;
  margin: 0;
}
.seller__name {
  font-size: 16px;
  color: white;
  margin: 0;
  font-weight: 300;
}
.price {
  color: white;
  font-size: 36px;
  font-weight: 700px;
  margin: 0;
}
.product__button {
  width: 100%;
  padding: 10px;
  font-size: 20px;
  font-weight: 700;
  border-radius: 10px;
  border: 2px solid #1095C9;
  background-color: transparent;
  color: white;
}
.product__button:hover {
  background: -webkit-linear-gradient(to right, #1095C9, #C51EED);
  background: linear-gradient(to right, #1095C9, #C51EED);
  border: 2px solid white;
  box-shadow: 0 0  10px 5px rgba(225, 225, 225, 0.2) ;
}
</style>