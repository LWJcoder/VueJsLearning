
<style>

  .modal-mask {
    position: fixed;
    z-index: 9998;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, .5);
    display: table;
    transition: opacity .3s ease;
  }

  /*垂直居中*/
  .modal-wrapper {
    display: table-cell;
    vertical-align: middle;
  }

  .modal-container {
    width: 40%;
    height: 30%;
    min-height: 250px;
    margin: 0 auto;
    margin-top: 100px;
    padding: 20px 30px;
    background-color: #fff;
    border-radius: 20px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, .33);
    transition: all .3s ease;
  }

  .modal-enter {
    opacity: 0;
  }

  .modal-leave-active {
    opacity: 0;
  }

  .modal-enter .modal-container,
  .modal-leave-active .modal-container {
    -webkit-transform: scale(1.1);
    transform: scale(1.1);
  }

.modal-header{
  display: inline-block;
  width: 100%;
  height: 50px;
  line-height: 50px;
}
.headerImg{
  display: inline-block;
  position: relative;
  left: 0;
  top: -58px;
  background-origin: border-box;
  background-position: center;
  background: url(../assets/imgs/headerImg.png) no-repeat;
  width: 85px;
  height: 115px;
    /* overflow: hidden; */
}

.payTxt{
    color:#848484;
    font-size: 12px;
}

.payInfo{
    font-size: 12px;
    color: #9d7144;
    position: relative;
    top: -102px;
    left: 15px;
    border: 1px solid #9d7144;
    padding: 5px 9px;
    border-radius: 5px; 
}

.payInfo::before{
    content: '';
    position: absolute;
    right: 100%;
    top: 7px;
    width: 0;
    height: 0;
    border: 6px solid transparent;
    border-right: 12px solid rgba(157, 113, 68, 0.4);
    color: rgba(157, 113, 68, 0.4);
}


.modal-body {
    /* top: -50%; */
    position: relative;
    top: -50px;
  }

</style>
<template>
    <transition name="modal" title="支付">
      <div class="modal-mask">
        <div class="modal-wrapper">
          <div class="modal-container">           
            <div class="modal-header "> 
               <i class="headerImg"></i>      
              <span class="c999 payInfo">弹窗</span>
            </div>
            <div class="modal-body">
              <Row>
                  <Row type="flex" align="middle" justify="center" >
                      <Col span="12" class="tc">  <img :src="imageSrc" alt="支付" class="qrCode"></Col>
                      <Col span="12" class="tc"> <img :src="imageSrc" alt="支付" class="qrCode"> </Col>               
                  </Row>
              </Row>
              <Row type="flex" align="middle" justify="center">
                  <Col span="12" class="payTxt tc">{{wxPay}} </Col>
                  <Col span="12"  class="payTxt tc"> {{zfbPay}} </Col>
              </Row>
            </div>

            <div class="modal-footer">
              <slot name="footer">
              
       
              </slot>
            </div>
          </div>
        </div>
      </div>

    </transition>  
</template>
<script>

export default {
    props:{imageSrc: String, 'payModalShow':Boolean},
    data() {
        return {
          wxPay: "微信支付",
          zfbPay: "支付宝支付",
          price: 10
        }
    },
   
}
</script>
