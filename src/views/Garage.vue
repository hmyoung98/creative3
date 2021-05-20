<template>
<div>
  <h1 class="garage">Your Garage</h1>
  <h3 v-if="this.$root.$data.garageSize===0" class="empty-garage">Your garage has no cars in it!</h3>
  <div v-else class="garage-container">
    <div class="garage-item" v-for="item in garage" :key="item.vin">
      <img v-bind:src="item.image"/>
      <p>{{item.make}}</p>
      <p>{{item.model}}</p>
      <p>{{item.year}}</p>
      <p>{{item.color}}</p>
      <button class="remove-button" v-on:click='removeItem(item)'>Remove</button>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'Garage',

  methods: {
    removeItem(item) {
      let index = this.$root.$data.garage.indexOf(item);
      this.$root.$data.garage.splice(index, 1);
      this.$root.$data.garageSize -= 1;
    }
  },

  computed: {
    garage() {
      return this.$root.$data.garage;
    }
  },
}
</script>
