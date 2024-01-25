<template>
  <div class="formContainer">
    <form class="form registerForm" @submit="handleSubmit">
      <h3>Register in Aerospace</h3>
      <Input className="registerInput" name="Full Name" required="true" />
      <Input className="registerInput" name="Username" required="true" />
      <Input className="registerInput" name="Email" required="true" />
      <Input className="registerInput" name="Password" required="true" />
      <Input className="registerInput" name="Phone Number" />
      <Buttons text="Submit" type="submit" className="btnSubmit" />
    </form>
  </div>
</template>

<script>
import Buttons from './Buttons.vue';
import Input from './Input.vue';

export default {
  components: {
    Buttons,
    Input,
  },
  methods: {
    handleSubmit(e) {
      e.preventDefault();
      console.log('Forms Submitted success');
    },
  },
};
</script>

<style>
.formContainer {
  width: min(400px, 100%);
  height: min(420px, 100%);
}

.registerForm h3 {
  color: #d12aff;
}

.registerForm {
  position: relative;
  width: 100%;
  height: 100%;
  background-color: #212121;
  border-radius: 10px;
  padding: 10px;
  display: flex;
  flex-direction: column;
  align-items: center;
  border: 2px solid #d12aff;
  box-shadow: 2px 2px 15px #d12aff;
}

.registerInput {
  width: 90%;
  height: 40px;
  margin-top: 5%;
}

.btnSubmit {
  position: absolute;
  bottom: 5%;
  width: 80%;
  background-color: black;
  box-shadow: 2px 2px 10px #d12aff;
  border: none;
  color: #d12aff;
}
</style>
