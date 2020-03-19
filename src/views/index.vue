<template>
    <div class="home">
        <div class="banner" id="home">
            <img src="../assets/images/banner.png" class="img-banner img-fluid">
            <h1 class="title">HOUSE OF TIME</h1>
            <h4 class="subtitle">Official Webpage</h4>
        </div>
        <section class="product">
            <div class="container-fluid container-product">
                <div class="row row-product">
                    <div class="col-md-3" v-for="(data, index) in products" :key="index">
                        <div class="product-item">
                            <div class="product-img text-center">
            <img :src="require(`../assets/images/${data.foto}`)" class="img-product"/>
                            </div>
                            <div class="product-detail text-center">
                                <h5><b>{{data.merk}}</b></h5>
                                <h6>{{data.harga}}</h6>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      products: [],
    };
  },
  async created() {
    const BASEURI = 'https://my-json-server.typicode.com/rifqiiardhian/dbuts/db';
    axios.get(BASEURI).then((result) => {
      this.products = result.data.products;
    });
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import '../css/style.css';
</style>
