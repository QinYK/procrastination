<template>
<div>
  <b-container>
        <div class="body_left">
            <img src="../assets/biubiubiu.gif" alt="" ondragstart='return false;'>
        </div>
        <div class="body_center love">
            <div class="block">
                <div class="div1"></div>
                <div class="div2"></div>
                <div class="div3"></div>
                <div class="div4"></div>
            </div>
        </div>
  </b-container>
</div>
</template>

<script>
import axios from 'axios'
export default {
  data () {
    return {
      randomNumber: 0
    }
  },
  methods: {
    getRandomFromBackend () {
    const path = 'http://localhost:5000/api/random';
    axios.get(path)
      .then(response => {
        this.randomNumber = response.data.randomNumber
      })
      .catch(error => {
        console.log(error)
      })
    },
    getRandom () {
      this.randomNumber = this.getRandomFromBackend()
    }
  },
  created () {
    this.getRandom()
  }
}
</script>
