<template>
  <div id="app">
    <Header />
    <!-- Hero Banner Starts -->
    <div class="hero-banner">
      <div class="download">
        Download the App
      </div>
      <div class="saving">
        Save up to 80% on your prescriptions instantly
      </div>
      <div class="grid">
        <img class="app" src="@/assets/BuzzRx-App.png" alt="BuzzRx App" />
        <div class="right-section">
          <div class="list">
            <div>
              <img class="check" src="@/assets/group.svg" alt="Check" />
              <span class="desc">
                On-the-go Savings
              </span>
            </div>
            <div>
              <img class="check" src="@/assets/group.svg" alt="Check" />
              <span class="desc">
                Price Alerts
              </span>
            </div>
            <div>
              <img class="check" src="@/assets/group.svg" alt="Check" />
              <span class="desc">
                Save your prescriptions
              </span>
            </div>
            <div>
              <img class="check" src="@/assets/group.svg" alt="Check" />
              <span class="desc">
                Set Refill Reminders
              </span>
            </div>
            <div>
              <img class="check" src="@/assets/group.svg" alt="Check" />
              <span class="desc">
                Locate Pharmacies
              </span>
            </div>
          </div>

          <div class="free-app">
            <span>
              Text me the FREE app!
            </span>
            <b-input-group>
              <b-input-group-prepend is-text>
                <img src="@/assets/text.svg" alt="phone" />
              </b-input-group-prepend>
              <b-form-input
                aria-label="Text input"
                placeholder="Enter Phone Number"
              ></b-form-input>
            </b-input-group>
            <button>
              GET THE APP
            </button>
            <div class="download-app">
              <img src="@/assets/app-store-badge.svg" alt="App Store" />
              <img src="@/assets/google-play-badge.svg" alt="Google Play" />
            </div>
          </div>
        </div>
      </div>
      <div class="info">
        <div class="as-seen">
          As seen on
        </div>
        <div class="compaines">
          <img src="@/assets/nbc-logo.svg" alt="NBC" />
          <img src="@/assets/cbs-logo.svg" alt="CBS" />
          <img src="@/assets/abc-logo.svg" alt="ABC" />
          <img src="@/assets/gma-logo.svg" alt="GMA" />
          <img src="@/assets/msnbc-logo.svg" alt="MSNBC" />
        </div>
      </div>
    </div>
    <!-- Hero Banner Ends -->
    <!-- Reviews Section Starts -->
    <div class="reviews-section-container">
      <div class="reviews-section">
        <div class="title">LATEST APP REVIEWS</div>

        <div class="reviews-container">
          <div v-for="(review, index) in reviewsToDisplay" :key="index">
            <Review :review="review" />
          </div>
        </div>
        <div class="read-more">
          <button class="read-more-btn">
            READ MORE REVIEWS
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Review from "./components/Review.vue";

export default {
  name: "App",
  components: {
    Header,
    Review
  },
  data() {
    return {
      index: 8,
      reviews: [
        "Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every",
        "Love this app! It saves me $24 on my prescription every month.",
        "Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every",
        "Love this app! It saves me $24 on my prescription every month.",
        "Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every month.",
        "Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every month.",
        "Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every month.Love this app! It saves me $24 on my prescription every",
        "Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every month.Love this app! It saves me $24 on my prescription every",
        "Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every",
        "Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every",
        "Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every",
        "aa",
        "ss",
        "ss",
        "Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every",
        " Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every",
        "Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every",
        "dsssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssd",
        "ff",
        "sdl"
      ]
    };
  },
  computed: {
    reviewsToDisplay() {
      let showArray = [];
      for (let i = this.index; i < this.index + 8; i++) {
        showArray.push(this.reviews[i]);
      }
      return showArray;
    }
  }
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Lato:wght@300;400&display=swap");
#app {
  font-family: "Lato", sans-serif;
}
.hero-banner {
  width: 100%;
  height: 375px;
  background: yellow;
  .download {
    padding-top: 40px;
    font-size: 54px;
    font: normal normal 300 54px/40px Omnes;
    text-align: center;
    color: #262626;
    letter-spacing: 0px;
  }
  .saving {
    padding-top: 10px;
    text-align: center;
    font: normal normal bold 24px/40px Lato;
    letter-spacing: 0px;
    color: #b33cc8;
  }
  .grid {
    display: flex;
    align-items: center;
    justify-content: center;
    padding-top: 15px;
    .app {
      width: 230px;
      height: 485px;
      margin-right: 70px;
    }
    .right-section {
      margin-left: 70px;
      display: flex;
      flex-direction: column;
      .list {
        margin-top: 25px;
      }
      .check {
        width: 24px;
        height: 21px;
        margin-right: 7px;
      }
      .desc {
        text-align: left;
        font: normal normal normal 18px/32px Lato;
        letter-spacing: 0px;
        color: #262626;
        opacity: 1;
      }
      .free-app {
        text-align: center;
        font: normal normal bold 18px/30px Lato;
        letter-spacing: 0px;
        color: #262626;
        opacity: 1;
        margin-top: 75px;
        margin-left: -25px;
        span {
          display: block;
          margin-bottom: 12px;
        }
        button {
          margin-top: 20px;
          width: 171px;
          height: 40px;
          background: #b33cc8 0% 0% no-repeat padding-box;
          border-radius: 28px;
          opacity: 1;
          border: none;
        }
        .download-app {
          margin-top: 40px;
          img {
            margin-left: 7px;
            margin-right: 7px;
          }
        }
      }
    }
  }
  .info {
    margin-top: 85px;
    .as-seen {
      text-align: center;
      font: normal normal normal 14px/30px Lato;
      letter-spacing: 0px;
      color: #262626;
      opacity: 1;
    }
    .compaines {
      margin-top: 20px;
      display: flex;
      align-items: center;
      justify-content: center;
      img {
        margin-left: 25px;
        margin-right: 25px;
      }
    }
  }
}
.reviews-section-container {
  width: 100%;
  background: #fef8e6 0% 0% no-repeat padding-box;
  .reviews-section {
    margin-top: 520px;
    width: 1325px;
    margin-left: auto;
    margin-right: auto;
    height: 928px;
    background: #fef8e6 0% 0% no-repeat padding-box;
    .title {
      padding-top: 25px;
      font: normal normal 600 20px/24px Lato;
      letter-spacing: 2px;
      color: #262626;
      text-transform: uppercase;
      opacity: 1;
      border-bottom: 3px solid #b33cc8;
      width: 237px;
      margin-left: auto;
      margin-right: auto;
      line-height: 30px;
    }
    .reviews-container {
      display: flex;
      justify-content: space-between;
      flex-wrap: wrap;
      width: 1300px;
    }
    .read-more {
      margin-top: 50px;
      display: flex;
      justify-content: center;
      align-items: center;
    }
    .read-more-btn {
      background: #b33cc8 0% 0% no-repeat padding-box;
      border-radius: 28px;
      opacity: 1;
      width: 228px;
      height: 40px;
      border: none;
    }
  }
}
</style>
