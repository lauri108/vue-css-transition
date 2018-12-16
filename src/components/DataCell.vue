<template>
  <div class="data-view">
    <div class="large-number" v-bind:class="fadeInAnimationClass">{{mainValue}}</div>
  </div>
</template>

<script>
export default {
  name: "DataCell",
  props: {
    mainValue: Number
  },
  data() {
    return {
      elementOpacity: 0.4,
      fadeInAnimationClass: ""
    };
  },
  watch: {
    mainValue() {
      console.log("watch updated");
      this.fadeInAnimationClass = "fadeIn";
    }
  },
  beforeUpdate() {
    console.log("lifecycle beforeUpdate");
  },
  updated() {
    console.log("lifecycle updated");
    this.fadeInAnimationClass = "";
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.large-number {
  font-size: 2em;
}
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

// .fade {
//    opacity: 1;
//    transition: opacity .25s ease-in-out;
//    -moz-transition: opacity .25s ease-in-out;
//    -webkit-transition: opacity .25s ease-in-out;
//    }
// .notfade {
//   opacity: 0.5
// }

/* The animation code */
@keyframes fadeInAnimation {
  from {
    opacity: 0.6;
  }
  to {
    opacity: 1;
  }
}

/* The element to apply the animation to */
.fadeIn {
  animation-name: fadeInAnimation;
  animation-duration: 1s;
}
</style>
