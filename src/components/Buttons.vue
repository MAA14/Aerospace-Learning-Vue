<template>
  <button
    class="btn"
    :class="className ?? ''"
    :id="idName ?? ''"
    @click="handleClick()"
    :type="type ?? ''"
  >
    {{ text }}
  </button>
</template>

<script>
export default {
  name: 'Buttons',
  props: {
    text: String,
    idName: String,
    className: String,
    type: String,
  },
  methods: {
    handleClick() {
      // Cegah error kalo kita gk masukin custom event
      if (this.$emit('btnClick')) {
        this.$emit('btnClick'); // Custom Event @btnClick="nameFunction()"
      }
    },
  },
};
</script>

<style>
.btn {
  border-radius: 10px;
  background-color: rgb(218, 218, 218);
  color: #212121;
  width: 100px;
  height: 50px;
  transition: all 0.5s ease-in;
  font-weight: bold;
  cursor: pointer;
  border: 2px solid white;
  box-shadow: 2px 2px 4px white;
  outline: none;
}

.btn:hover {
  background-color: #212121;
  color: #ff14dc;
  border: 2px solid #212121;
  box-shadow: 2px 2px 4px #ff14dc;
}
</style>
