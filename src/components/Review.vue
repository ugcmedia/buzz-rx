<template>
  <div class="card">
    <div class="thumbail">
      <img src="@/assets/Path.svg" alt="Thumbnail" />
      <span>J</span>
    </div>
    <div class="name">
      John Smith
    </div>
    <div class="ratings">
      Rating
    </div>
    <div class="date">
      September 14, 2020
    </div>
    <div class="review">
      {{ review }}
    </div>
  </div>
</template>

<script>
export default {
  name: "Review",
  props: {
    review: {
      type: String,
      default: "Love this app! It saves me $24 on my prescription every month."
    }
  }
};
</script>

<style lang="scss" scoped>
.card {
  padding: 15px;
  width: 280px;
  min-height: 239px;
  box-shadow: 0px 3px 6px #00000029;
  text-align: center;
  border-radius: 25px;
  margin: 22px 22px;
  .thumbail {
    margin-top: 10px;
    span {
      position: absolute;
      font-size: 28px;
      margin-left: -32px;
      color: #ffffff;
    }
  }
  .name {
    margin-top: 8px;
    text-align: center;
    font: normal normal normal 18px/30px Lato;
    letter-spacing: 0px;
    color: #262626;
    opacity: 1;
  }
  .ratings {
    margin-top: 12px;
    background: #b33cc8 0% 0% no-repeat padding-box;
    opacity: 1;
  }
  .date {
    font: normal normal normal 14px/30px Lato;
    letter-spacing: 0px;
    color: #707070;
    opacity: 1;
  }
  .review {
    margin-top: 12px;
    font: normal normal normal 16px/20px Lato;
    letter-spacing: 0px;
    color: #262626;
    opacity: 1;
    flex-wrap: wrap;
  }
}
</style>
