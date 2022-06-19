<template>
 <h1>{{ name }}</h1>
 <input v-model="start"/>
 <button @click="shiftColor()">SHIFT</button>
 <p>Complementary: {{ result }}</p>
</template>

<script>
export default {

  name: 'HeadingText',
  props: ['name'],

  data() {
    return {
       start: '',
       result: ''
    };
  },
  methods: {
    shiftColor(){
      var tinycolor = require("tinycolor2");
      console.log(this.start);
      this.result = tinycolor(this.start).complement().toHexString();
    }
  }  
}
</script>

<style lang="scss">
@import '../sass/main.scss';
</style>