<template>
  <h2>{{ title ? title : 'TESTE' }}</h2>
  <p>{{ counter }}<sup>2</sup> = {{ squaredCounter }}</p>
  <div>
    <button @click="increase">+1</button>
    <button @click="decrease">-1</button>
  </div>
</template>

<script>

export default {
  props: {
    title: String,
    start: {
      type: Number,
      default: 100,

      validator(value) {
        return value >= 0
      }
    }
  },

  data() {
    return {
      counter: this.start
    }
  }, methods: {
    getSquaredValue() {
      return 'hola mundo';
    },
    increase() {
      this.counter = this.counter + 1
    },
    decrease() {
      this.counter = this.counter - 1
    }
  }, computed: {
    squaredCounter() {
      return this.counter * this.counter;
    }
  },
}

</script>

<style>
button {
  background-color: #64B687;
  border-radius: 5px;
  border: 1px solid white;
  color: white;
  cursor: pointer;
  margin: 0 5px;
  padding: 5px 15px;
  transition: 0.3s ease-in-out;
}

button:hover {
  background-color: #5aa67b;
  transition: 0.3s ease-in-out;
}
</style>