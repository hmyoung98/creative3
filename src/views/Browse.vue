<template>
<div>
  <div class="pure-menu pure-menu-horizontal">
    <ul class="pure-menu-list">
      <li class="pure-menu-item"><a @click="select('United States')" href="#" class="pure-menu-link">United States</a></li>
      <li class="pure-menu-item"><a @click="select('Canada')" href="#" class="pure-menu-link">Canada</a></li>
      <li class="pure-menu-item"><a @click="select('Mexico')" href="#" class="pure-menu-link">Mexico</a></li>
      <li class="pure-menu-item"><a @click="select('Brazil')" href="#" class="pure-menu-link">Brazil</a></li>
    </ul>
  </div>
  <CarList :cars="cars" />
</div>
</template>

<script>
import CarList from "../components/CarList.vue"
export default {
  name: 'Browse',
  components: {
    CarList
  },
  data() {
    return {
      model: '',
    }
  },
  computed: {
    cars() {
      return this.$root.$data.cars.filter(car => car.model === this.model);
    }
  },
  methods: {
    select(model) {
      this.model = model;
    }
  }
}
</script>
