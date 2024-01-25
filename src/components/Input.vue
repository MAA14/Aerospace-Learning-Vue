<template>
  <div class="inputContainer" :class="className ?? ''" :id="idName ?? ''">
    <input
      type="text"
      :name="name"
      :required="required ?? false"
      ref="input"
      :placeholder="required ? '' : 'You can choose to not fill'"
    />
    <label for="name" @click="handleClickLabel">{{
      'Input your ' + name
    }}</label>
  </div>
</template>

<script>
export default {
  props: {
    name: String,
    className: String,
    idName: String,
    required: Boolean,
  },
  methods: {
    handleClickLabel() {
      this.$refs.input.focus();
    },
  },
};
</script>

<style>
.inputContainer {
  position: relative;
}

.inputContainer input {
  width: 100%;
  height: 100%;
  font-size: 14px;
  border-radius: 10px;
  outline: none;
  background-color: #212121;
  color: #d12aff;
  border: 2px solid black;
  padding: 5px;
}

.inputContainer label {
  position: absolute;
  font-size: 12px;
  color: #d12aff;
  font-weight: bolder;
  top: 40%;
  left: 5%;
  background-color: #212121;
  padding-left: 5px;
  padding-right: 5px;
  transition: all 0.3s ease-in;
}

.inputContainer input:focus ~ label,
.inputContainer input:valid ~ label {
  top: -10%;
  left: 2%;
}
</style>
