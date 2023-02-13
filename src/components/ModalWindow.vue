<template>
  <div class="modal" v-if="show" @click="hideModal">
  <div @click.stop class="modal-content">
  <div class="inputs">
  <user-input @pass-value="setFirstInputValue" :value="firstInputValue" :placeholder="firstInputPlaceholder"/>
  <user-input @pass-value="setSecondInputValue" :value="secondInputValue" :placeholder="secondInputPlaceholder"/>
  </div>
  <my-button @click="onClick">CLICK</my-button>
  </div>
  </div>
</template>

<script>
import UserInput from "./UI/UserInput"
import MyButton from "./UI/MyButton"

export default {
    components: {
      UserInput, MyButton
    },
    props: {
      show: {
        type: Boolean,
        default: false
      }
    },
    data() {
        return {
          firstInputPlaceholder: "A",
          secondInputPlaceholder: "B",
          firstInputValue: "",
          secondInputValue: "",
        }
    },
    methods: {
      setFirstInputValue(InputValue){
        this.firstInputValue = InputValue
      },
      setSecondInputValue(InputValue){
        this.secondInputValue = InputValue
      },
      onClick(){
        console.log("A väli: ",this.firstInputValue || "tühi")
        console.log("B väli: ",this.secondInputValue || "tühi")
        this.firstInputValue = ""
        this.secondInputValue = ""
      },
      hideModal() {
        this.$emit('update:show', false)
      }
    }
}

</script>

<style>
.modal{
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  background: rgba(0, 0, 0, 0.5);
  
  display: flex;
  position: fixed;
  align-items: center;
  justify-content: center;
}
.modal-content{
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  padding: 50px clamp(1.5rem, 3vw, 5rem);
  border-radius: 12px;
  background: white;
  max-width: 80vw;
}
.inputs{
  max-width: 300px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>