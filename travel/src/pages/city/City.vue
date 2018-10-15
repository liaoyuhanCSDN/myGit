<template>
    <div>
        <city-header></city-header>
        <city-search></city-search>
        <city-list :list="hotCities" :cities="cities" :letter="letter"></city-list>
        <city-alphabet :cities="cities" @change="handleLetterChange"></city-alphabet>
    </div>
</template>

<script>
import axios from 'axios'
import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityList from './components/List'
import CityAlphabet from './components/Alphabet'
export default {
  name: 'City',
  data () {
      return {
          cities: {},
          hotCities: [],
          letter: ''
      }
  },
  components: {
      CityHeader,
      CitySearch,
      CityList,
      CityAlphabet
  },
  mounted () {
      this.getCityInfo ()
  },
  methods: {
     getCityInfo () {
         axios.get('api/city.json')
           .then(this.handleGetCityInfoSucc)
     },
     handleGetCityInfoSucc (res) {
          res = res.data 
          if (res.ret && res.data) {
              const data = res.data 
              this.hotCities = data.hotCities
              this.cities = data.cities
          }
     },
     handleLetterChange (letter) {
         if (letter) {
           this.letter = letter
         }
     }
  }
}
</script>

<style>

</style>
