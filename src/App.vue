<script setup>
// Session 1 Challenge - Animated Cats!

// Use Class & Attribute bindings to give each cat a color and animation, matching their text description.

// Use the provided class names for the animations and
// `background-color` style attr for colors - remember that 'red', 'green' etc are valid html color values!

// The values you need are inside the cat objects, so double check their structure!

// All of your changes should be within the `<template>` tag
// (except the bonus question)

// Data (Cat objects)
// remember: don't modify these cat objects, they are very touchy!
// level 1
const happyCat = {
  class: 'joyful',
  style: 'background-color: red;',
};

// level 2
const cheekyCat = {
  anim: { twisty: true },
  color: 'green',
};

// level 3
const lolCat = {
  isSpinning: true,
  getColor: () => 'yellow',
};

// level 4
const sadCat = {
  isClass: (className) => {
    return className === 'wobbly';
  },
  isColor: (color) => {
    return color === 'blue';
  },
};

// bonus level:
// what would be the best approach to apply the following style:
// border-radius: 50%;
// to ALL cats?
// (please reason your answer)

function backgroundColor(color) {
  return `background-color: ${color}`
}

function circle() {
  return 'border-radius: 50%';
}

</script>

<template>
  <ol>
    <li>
      <div class="cat" :class="happyCat.class" :style="[circle(), happyCat.style]">😺</div>
      I'm joyful and red
    </li>
    <li>
      <span class="cat" :class="cheekyCat.anim.twisty ? 'twisty' : ''" :style="[backgroundColor(cheekyCat.color) , circle()]">😼</span>
      I'm twisty and green
    </li>
    <li>
      <span class="cat" :class="lolCat.isSpinning ? 'spinning' : ''" :style="[backgroundColor(lolCat.getColor()), circle()]">😹</span>
      I'm spinning and yellow
    </li>
    <li>
      <span class="cat" :class="sadCat.isClass('wobbly') ? 'wobbly' : ''" :style="[sadCat.isColor('blue') ? backgroundColor('blue') : '', circle()]">😿</span>
      I'm wobbly and blue
    </li>
  </ol>
</template>
<!-- :style="[backgroundColor(cheekyCat.color) , circle()]" -->
<style scoped>
/* dont change these classes either :) */
li {
  margin: 2em 0;
}

.cat {
  font-size: 4rem;
  display: inline-block;
  vertical-align: middle;
  margin-right: 0.5em;
  animation-iteration-count: infinite;
  animation-duration: 1s;
  animation-fill-mode: both;
}

.joyful {
  animation-name: joyful;
}

.wobbly {
  animation-name: wobbly;
}

.twisty {
  animation-name: twisty;
  transform-origin: center;
}

.spinning {
  animation-name: spin;
}
</style>
