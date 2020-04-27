<template>
  <div class="container">
      こんにちは！ {{ testText }}

  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import axios from 'axios';

export default Vue.extend({
  data: function(){
    return {
      testText: null,
    }
  },
  components: {
  },
  created: function(){
    axios.get('/test.txt')
    .then((response: any) => {
        // handle success
      console.log(response);
      this.testText = response.data;
    })
    // .catch(function (error) {
    //     // handle error
    //   console.log(error);
    // })
    // .finally(function () {
    //     // always executed
    // });
  }
})
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}



</style>
