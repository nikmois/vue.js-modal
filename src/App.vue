<template>
    <div class="app">
        <my-button class="btn" @click="showModal">Nupp 1</my-button>
        <modal-window v-model:show="modalVisible"/>
        
    </div>
</template>

<script>
import ModalWindow from "@/components/ModalWindow";
import MyButton from "@/components/UI/MyButton";

export default {
    components: {
        ModalWindow, MyButton
    },
    data() {
        return {
            modalVisible: false,
        }
    },
    methods: {
        showModal() {
            this.modalVisible = true
        }
    }
}
</script>

<style>
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
.app{
    background: rgb(211, 211, 252);
    width: 100%;
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
}
</style>