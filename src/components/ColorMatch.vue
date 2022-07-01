<!--
Color Matcher by Alexander Abraham,
a.k.a. "The Black Unicorn", a.k.a. "Angeldust Duke".
Licensed under the MIT license.
-->

<template>

 <!--
  The main component for retrieving input
  and changing the paragraph's text.
 -->
 <div class="content">
  <h1>{{ name }}</h1>
  <input v-model="start" placeholder="Gimme your color!"/>
  <button @click="shiftColor()">SHIFT</button>
  <p>Complementary: {{ result }}</p>
 </div>

</template>

<script>
export default {

  name: 'HeadingText',
  props: ['name'],

  data() {

    // Setting up the app-wide
    // variables.
    return {
       start: '',
       result: ''
    };

  },
  methods: {

    // A function to shift the color
    // on pressing a button.
    shiftColor(){
      var tinycolor = require("tinycolor2");
      console.log(this.start);
      this.result = tinycolor(this.start).complement().toHexString();
    }

  }  
}
</script>

<style lang="scss">

// Defining the font scheme
// and color scheme.
$stdFont: monospace;
$mainColor: #000000;
$accentColor: #FFFFFF;
$shadowColor: #808080;


/* DESKTOP SECTION START */
html, body {
    top: 0;
    right: 0;
    left: 0;
    bottom: 0;
    padding: 0px;
    margin: 0px;
    width: 100vw;
    height: 100vh;
    box-sizing: border-box;
}

div.content {
    margin: 0 auto;
    display: block;
    width: 60%;
    border-radius: 25px;
    border: 5px solid $mainColor;
    padding: 10px;
    box-shadow: 1px 2px 15px $shadowColor;
}

h1 {
    font-size: 45px;
    color: $mainColor;
    font-family: $stdFont;
    text-align: center;
    padding: 0px;
    margin-top: 0px;
    margin-bottom: 10px;
    margin-left: 0px;
    margin-right: 0px;
}

input {
    display: block;
    width: 63%;
    border: 3px solid $mainColor;
    font-size: 30px;
    color: $mainColor;
    background-color: $accentColor;
    border-radius: 15px;
    margin: 0 auto;
    margin-top: 0px;
    margin-bottom: 10px;
    font-family: $stdFont;
    padding: 10px;
    text-align: left;
}

input:focus {
    outline: none;
}

button {
    display: block;
    width: 66%;
    border: 3px solid $mainColor;
    font-size: 30px;
    color: $accentColor;
    background-color: $mainColor;
    border-radius: 15px;
    margin: 0 auto;
    font-family: $stdFont;
    margin-top: 0px;
    margin-bottom: 10px;
    padding: 10px;
    transition-duration: 0.6s;
    text-align: center;
}

button:hover {
    padding: 15px;
    color: $mainColor;
    background-color: $accentColor;
}

p {
    display: block;
    width: 60%;
    border: 3px solid $mainColor;
    font-size: 25px;
    color: $mainColor;
    background-color: $accentColor;
    border-radius: 15px;
    font-family: $stdFont;
    margin: 0 auto;
    margin-top: 0px;
    margin-bottom: 10px;
    padding: 20px;
    text-align: left;
}
div.footer {
  width: 100vw;
  border-top: 3px solid $mainColor;
  border-bottom: none;
  border-right: none;
  border-left: none;
  bottom: 0;
  right: 0;
  left: 0;
  margin: 0px;
  padding: 10px;
  position: fixed;
  background-color: transparent;
}
p.footer {
  text-align: center;
  border: none;
  font-family: $stdFont;
  color: $mainColor;
  font-size: 25px;
  padding: 0px;
  margin: 0px;
  text-align: center;
  font-style: italic;
  width: auto;
}

a {
  font-family: $stdFont;
  color: $mainColor;
  font-size: 25px;
  padding: 0px;
  margin: 0px;
  text-align: center;
  font-style: italic;
  transition-duration: 0.6s;
}

a:hover {
     color: $shadowColor;
}

/* DESKTOP SECTION END */

/* MOBILE SECTION START */
@media screen and (max-width: 800px){
    div.content {
        width: 75%;
    }
    button {
        width: 75%;
    }
    h1 {
        font-size: 30px;
    }
    input {
        overflow-x: scroll;
        font-size: 20px;
        width: 69%;
    }
    button {
        font-size: 20px;
    }
    p {
        font-size: 20px;
        overflow-x: scroll;
        width: 63%;
    }
    p.footer {
        font-size: 20px;
    }
    a {
        font-size: 20px;
    }
}
/* MOBILE SECTION END */
</style>
