<template>
  <div>
    <b-modal id="text-modal" hide-header hide-footer centered>
      <div class="text-modal-content">
        <img src="@/assets/buzz-rx.svg" alt="Buzz RX" />
        <div class="text-sent">Text Sent</div>
        <div class="info-text">
          Click the link that was sent to your mobile device to download the
          FREE BuzzRx app!
        </div>
        <button class="ok-btn" @click="$bvModal.hide('text-modal')">
          OK
        </button>
      </div>
    </b-modal>
  </div>
</template>

<script>
export default {
  name: "Modal"
};
</script>

<style lang="scss" scoped>
.text-modal-content {
  margin-top: 15px;
  text-align: center;
  .text-sent {
    margin-top: 15px;
    font: normal normal 900 30px/34px Lato;
    letter-spacing: 0px;
    color: #262626;
    opacity: 1;
    font-size: 30px;
    color: #262626;
  }
  .info-text {
    margin-top: 20px;
    margin-bottom: 10px;
    font: normal normal medium 18px/22px Lato;
    letter-spacing: 0px;
    opacity: 1;
    color: #262626;
  }
  .ok-btn {
    width: 97px;
    height: 45px;
    margin: 20px 0px;
    outline: none;
    border: none;
    background: #ffc700 0% 0% no-repeat padding-box;
    border-radius: 23px;
    opacity: 1;
  }
}
</style>
