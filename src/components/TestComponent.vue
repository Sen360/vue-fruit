<template>
  <div>
    <input
      :class="{
        'border-green': fruitInput !== '',
        'border-red': fruitInput === '',
      }"
      v-model="fruitInput"
    />
    <button @click="handleClick">Add fruit</button>
    <div v-show="isDivShown">
      <span>{{ message }}</span>
    </div>
    <div v-for="fruit in fruits" :key="fruit.name">{{ fruit.name }}</div>
  </div>
</template>

<script>
export default {
  name: "TestComponent",
  data() {
    return {
      isDivShown: false,
      fruitInput: "",
      fruits: [{ name: "Tomato" }, { name: "Carrot" }, { name: "Tomi" }],
    };
  },
  methods: {
    handleClick() {
      this.isDivShown = !this.isDivShown;
      this.fruits.push({ name: this.fruitInput });
    },
  },
};
</script>

<style>
.border-green {
    border: 1px solid green;
}

.border-red {
    border: 1px solid red;
}
</style>
