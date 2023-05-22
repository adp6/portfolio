<template>
<ButtonVue :func="()=>{open=true}" name="Contact me" />

<div v-if="open" class="modal">
  <Popper content="Copied to Clipboard" placement="top" closeDelay="100" :interactive=false>
  <p>Contact me on <span @click="copy">{{ email }}</span></p>
  </Popper>
  <ButtonVue :func="()=>{open=false}" name="Close" />
</div>
</template>

<style scoped>
.modal {
  position: fixed;
  z-index: 999;
  top: 20%;
  text-align: center;
  left: 50%;
  width: 300px;
  margin-left: -150px;
  background-color: rgb(0, 0, 0);
  border-radius: 20px;
  padding: 20px;
}
span{
  text-decoration: underline;
  cursor: pointer;
}
p{
  padding: 20px;
}

:deep(.popper) {
        background: #4d7bc4;
        padding: 20px;
        border-radius: 20px;
        color: rgb(209, 209, 209);
        font-weight: bold;
        text-transform: uppercase;
    }

    :deep(.popper #arrow::before) {
        background: #e92791;
    }

    :deep(.popper:hover),
    :deep(.popper:hover > #arrow::before) {
        background: rgb(199, 155, 78);
        color: black;
    }

</style>

<script>
import ButtonVue from './ButtonVue.vue';
import Popper from 'vue3-popper';
export default {
  name:'ModalWindowVue',
  data(){
    return{
      open:false,
      email:'mcdegan244@gmail.com'
    }
  },
  methods:{
    copy(){
      navigator.clipboard.writeText(this.email);

    }
  },
  components:{
    ButtonVue,
    Popper
  }
}
</script>