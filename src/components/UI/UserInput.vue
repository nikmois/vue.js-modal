<template>
  <input
    v-model="InputValue"
    @input="$emit('passValue', InputValue)"
    type="text"
    :placeholder="placeholder"
  />
</template>

<script>
export default {
  props: {
    placeholder: {
      type: String,
      required: true,
    },
  },
  data() {
    return {
      InputValue: "",
    };
  },
};
</script>

<style>
input {
  margin: 1rem;
  font-size: 1rem;
  padding: 5px;
  width: 100%;
  height: 56px;
  border: 2px solid rgb(113, 113, 255);
  border-radius: 4px;
  position: relative;
  background-color: rgba(255, 255, 255, 0.3);
  transition: 0.3s background-color ease-in-out;
}
input:focus{
background-color: rgba(168, 205, 253, 0.45);
}

input:hover {
 background-color: rgba(168, 205, 253, 0.45);
}
</style>