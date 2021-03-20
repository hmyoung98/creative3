<template>
<div>
  <div class="pure-menu pure-menu-horizontal">
    <ul class="pure-menu-list">
      <li class="pure-menu-item"><a @click="select('1960-1980')" href="#" class="pure-menu-link">-1980</a></li>
      <li class="pure-menu-item"><a @click="select('1980-1990')" href="#" class="pure-menu-link">1980-1990</a></li>
      <li class="pure-menu-item"><a @click="select('1990-2010')" href="#" class="pure-menu-link">1990-2000</a></li>
      <li class="pure-menu-item"><a @click="select('2000-2010')" href="#" class="pure-menu-link">2000-2010</a></li>
      <li class="pure-menu-item"><a @click="select('2010-present')" href="#" class="pure-menu-link">2010-present</a></li>
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
      year: '',
    }
  },
  computed: {
    cars() {
      return this.$root.$data.cars.filter(car => car.year === this.year);
    }
  },
  methods: {
    select(year) {
      this.year = year;
    }
  }
}
</script>
