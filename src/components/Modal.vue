<template>
  <div class="modalContainer" :class="className" :id="idName">
    <slot></slot>
    <div class="closeModal" @click="handleClick()">
      <p>Click Here to Close</p>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    handleClick() {
      this.$emit('close');
    },
  },
  props: {
    className: String,
    idName: String,
  },
};
</script>

<style>
.modalContainer {
  position: fixed;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 1);
  display: flex;
  justify-content: center;
  flex-direction: row;
  transition: all 0.3s ease-in;
}

.closeModal {
  font-family: monospace;
  position: absolute;
  bottom: 5%;
  cursor: pointer;
}

.closeModal p {
  font-size: 14px;
  color: white;
  opacity: 1;
  animation: sprinkle 3s 0s infinite ease-in-out;
}

.modalContainer.close {
  transform: scale(0);
}

.modalContainer.show {
  transform: scale(1);
}

@keyframes sprinkle {
  0% {
    opacity: 1;
  }

  50% {
    opacity: 0.2;
  }

  100% {
    opacity: 1;
  }
}
</style>
