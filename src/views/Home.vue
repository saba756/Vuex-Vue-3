<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <Counter />
    <CounterSquared />
    <Buttons />
    <div>
      <input v-model="colorCode" type="text" placeholder="type color code" />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Counter from "../components/Counter.vue";
import CounterSquared from "../components/CounterSquare.vue";
import Buttons from "../components/Buttons.vue";
export default {
  name: "Home",
  components: {
    Counter,
    CounterSquared,
    Buttons,
  },
  computed: {
    colorCode: {
      get() {
        return this.$store.state.colorCode;
      },
      set(newValue) {
        return this.$store.dispatch("setColorCode", newValue);
      },
    },
  },
};
</script>
<style>
div {
  margin-bottom: 10px;
}
.counter {
  font-size: 80px;
}
.buttons button {
  font-size: 40px;
  width: 100px;
  margin: 0px 10px;
}
</style>