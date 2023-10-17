<template> 
    <h1>{{ msg }}</h1>

    <div v-for ="el in product.id"  class="product_details">   
      <h3> name: {{ this.product.name }}</h3>     
      <h3> prise: {{ formattedPrice }}</h3>      
      <h4 v-if="this.product.available > 0">available: Available</h4>  
      <h4 v-else>available: Out of stock</h4>  
    </div>
</template>


<script>
export default {
  name: 'ProductDetails',
  props: {
    msg: String,
    available: Number,
  },

  data() {   
    return {  
        product:     
        {id: 1, name: 'product_new', price: 2500, available: `${this.available}`}
    }
  },
    computed: {
      formattedPrice() {
        return this.product.price = `$${this.product.price}`;    
      } 
  },
}
</script>

<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
