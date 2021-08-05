<template>
  <div class="card card-body m-4">
    <h3>Compostion API + Vuex</h3>
    <h5 class="text-center">{{ counter }} x 2 = {{ times2 }}</h5>
    <button class="btn btn-primary" @click="inc">Increment</button>
  </div>
</template>

<script>
import { useState, useGetters, useMutations } from "@/helpers";

export default {
  setup() {
    const { counter } = useState(["counter"]);
    console.log(counter)
    const { times2 } = useGetters(["times2"]);
    const { setCounter } = useMutations(["setCounter"]);
    const inc = () => setCounter(counter.value + 1)
    return { counter, times2, inc };
  },
};
</script>