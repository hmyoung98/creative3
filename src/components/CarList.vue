<template>
<div class="wrapper">
  <div class="cars">
    <div class="car" v-for="car in cars" :key="car.vin">
      <div class="info">
        <h1>{{car.make}}</h1>
	<h2>{{car.model}}</h2>
	<p><em>{{car.year}}</em></p>	
      </div>
      <div class="image">
        <img :src="'/images/car-pics/'+car.image">
      </div>
      <div class="price">
        <h2>{{car.price}}</h2>
        <button class="auto" v-on:click="addToGarage(car)">Add to Garage</button>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'CarList',
  props: {
    products: Array
  },
  methods: {
    addToGarage(car){
      this.$root.$data.garage.push(car);
      this.$root.$data.garageSize += 1;
    }
  }
}
</script>

<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}

.cars {
  margin-top: 20px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

.car {
  margin : 10px;
  margin-top: 50px;
  width: 200px;
}

.car .image {
  display: flex;
  justify-content: center;
  margin-bottom: 5px;
}

.info {
  background: DF0E46;
  color: whitesmoke;
  padding: 10px 30px;
  height: 80px;
}

.info h1 {
  font-size: 16px;
}

.info h2 {
  font-size: 14px;
}

.info p {
  margin: 0px;
  font-size: 10px;
}

button {
  height: 50px;
  background: #000;
  color: whitesmoke;
  border:none;
}

.auto {
  margin-left: auto;
}
</style>
