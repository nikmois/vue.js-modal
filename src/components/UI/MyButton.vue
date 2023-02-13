<template>
  <button>
      <slot></slot>
  </button>
</template>

<script>
export default {

}
</script>

<style>
button {
  background-image: linear-gradient(-180deg, #37AEE2 0%, #1E96C8 100%);
  border-radius: .5rem;
  box-sizing: border-box;
  color: #FFFFFF;
  display: flex;
  font-size: 16px;
  font-weight: 600;
  justify-content: center;
  padding: 1rem 1.75rem;
  text-decoration: none;
  width: 100%;
  max-width: 250px;
  border: 0;
  cursor: pointer;
  margin: 1rem;
}

button:hover {
  background-image: linear-gradient(-180deg, #1D95C9 0%, #17759C 100%);
}

</style>