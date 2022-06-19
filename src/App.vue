<!--
Color Matcher by Alexander Abraham,
a.k.a. "The Black Unicorn", a.k.a. "Angeldust Duke".
Licensed under the MIT license.
-->

<template>

 <!--
  The main component uniting
  everything.
 -->
 <LineBreak/>
 <LineBreak/>
 <ColorMatch name="Color Match" />

</template>

<script>

// Importing the components and
// including them.
import ColorMatch from './components/ColorMatch.vue';
import LineBreak from './components/LineBreak.vue';
export default {
  name: 'App',
  components: {
    ColorMatch,
    LineBreak
  },
}
</script>