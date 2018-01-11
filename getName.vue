<style>

</style>


<template>
   <div>          
    <modal payModalShow="false" v-if="payModalShow"   imageSrc="./src/assets/imgs/QRcode.png">   </modal>
    </div>
   </template>
    
<script>
import modal from "../../components/payModal";
export default {
  components: { modal },
  data() {
    return {
    

      isshow: false,
      payModalShow: false
    };
  },
  methods: {
    nameHide() {
      this.isshow = !this.isshow;
    },
    showName() {
      this.isshow = true;
    },
    payMonney() {
      console.log(this.payModalShow);
      this.payModalShow = true;
      console.log(this.payModalShow);
    }
  }
};
</script>
    
    