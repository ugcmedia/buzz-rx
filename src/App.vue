<template>
  <div id="app">
    <Header />
    <!-- Hero Banner Starts -->
    <div class="hero-banner">
      <div class="download">
        Download the App
      </div>
      <div class="saving">
        Save up to 80% on your prescriptions instantly!
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
                Save your Prescriptions
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
                v-model="fNumber"
                @input="serializeOne"
              ></b-form-input>
            </b-input-group>
            <button class="get-app-btn" @click="$bvModal.show('text-modal')">
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

        <div id="reviews" class="reviews-container slide-in">
          <div v-for="(review, index) in reviewsToDisplay" :key="index">
            <Review :review="review" />
          </div>
        </div>
        <div v-if="rIndex < 21" class="read-more">
          <button class="read-more-btn" @click="loadReviews">
            READ MORE REVIEWS
          </button>
        </div>
        <div v-if="rIndex > 20" class="read-more">
          <button class="read-more-btn" @click="goBack">
            Go Back
          </button>
        </div>
      </div>
    </div>
    <!-- Reviews Section Ends -->
    <!-- App Perks Section Starts -->
    <div class="app-perks-section">
      <div class="title">USING THE BUZZRX APP</div>
      <div class="screens-container">
        <div class="single-screen">
          <div class="benefit-title">
            1. SEARCH BY DRUG NAME
          </div>
          <div class="description">
            Type in your prescription drug name and select your dosage.
          </div>
          <img class="screen" src="@/assets/screen-1.png" alt="Search Image" />
        </div>
        <div class="single-screen">
          <div class="benefit-title">
            2. CHOOSE THE BEST PRICE
          </div>
          <div class="description">
            Select the best price at a participating pharmacy near you.
          </div>
          <img class="screen" src="@/assets/screen-2.png" alt="Price Image" />
        </div>
        <div class="single-screen">
          <div class="benefit-title">
            3. SHOW YOUR COUPON
          </div>
          <div class="description">
            Show the coupon to your pharmacist directly from the app.
          </div>
          <img class="screen" src="@/assets/screen-3.png" alt="Coupon Image" />
        </div>
        <div class="single-screen">
          <div class="benefit-title">
            4. SAVE YOUR FAVORITES
          </div>
          <div class="description">
            Save the prescription discount coupons to your favorites
          </div>
          <img class="screen" src="@/assets/screen-4.png" alt="Fav Image" />
        </div>
      </div>
    </div>
    <!-- App Perks Section Ends -->
    <!-- Footer -->
    <div class="footer-cotainer">
      <div class="footer-content">
        <div class="left">
          <div class="heading">Never Pay Full Price at the Pharmacy Again</div>
          <div class="save">
            Get the FREE BuzzRx app and save today!
          </div>
          <div class="download-app">
            <img src="@/assets/app-store-badge.svg" alt="App Store" />
            <img src="@/assets/google-play-badge.svg" alt="Google Play" />
          </div>
        </div>
        <div class="right">
          <span>
            Text me the FREE app!
          </span>
          <div>
            <b-input-group>
              <b-input-group-prepend is-text>
                <img src="@/assets/text.svg" alt="phone" />
              </b-input-group-prepend>
              <b-form-input
                aria-label="Text input"
                placeholder="Enter Phone Number"
                v-model="sNumber"
                @input="serializeTwo"
              ></b-form-input>
            </b-input-group>
          </div>
          <button @click="$bvModal.show('text-modal')">
            GET THE APP
          </button>
        </div>
      </div>
    </div>
    <Modal />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Review from "./components/Review.vue";
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: {
    Header,
    Review,
    Modal
  },
  data() {
    return {
      fNumber: "",
      sNumber: "",
      rIndex: 0,
      reviews: [
        {
          stars: 5,
          text: "Love this app! It saves me $24 on my prescription every month."
        },
        {
          stars: 4,
          text:
            "Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every month."
        },
        {
          stars: 5,
          text: "Love this app! It saves me $24"
        },
        {
          stars: 3,
          text:
            "Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every month."
        },
        {
          stars: 4,
          text:
            "Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24"
        },
        {
          stars: 3,
          text: "Love this app! It saves me $24"
        },
        {
          stars: 4,
          text:
            "Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24"
        },
        {
          stars: 5,
          text:
            "Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every month."
        },
        {
          stars: 3,
          text:
            "Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24"
        },
        {
          stars: 4,
          text: "Love this app! It saves me $24"
        },
        {
          stars: 5,
          text:
            "Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24"
        },
        {
          stars: 5,
          text:
            "Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every month."
        },

        {
          stars: 3,
          text: "Love this app! It saves me $24 on my prescription every month."
        },

        {
          stars: 4,
          text:
            "Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every month."
        },

        {
          stars: 3,
          text: "Love this app! It saves me $24"
        },

        {
          stars: 4,
          text:
            "Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every month."
        },
        {
          stars: 3,
          text: "Love this app! It saves me $24 on my prescription every month."
        },
        {
          stars: 5,
          text:
            "Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every month."
        },
        {
          stars: 4,
          text:
            "Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every month."
        },
        {
          stars: 5,
          text:
            "Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24"
        },
        {
          stars: 3,
          text:
            "Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24"
        },
        {
          stars: 4,
          text:
            "Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every month. Love this app! It saves me $24 on my prescription every month."
        }
      ],
      reviewsToDisplay: []
    };
  },
  mounted() {
    let el = document.getElementById("reviews");
    el.addEventListener("webkitAnimationEnd", () => {
      el.classList.remove("slide-in");
    });
    this.loadReviews();
  },
  computed: {
    reviewsAvailable() {
      return true;
    }
  },
  methods: {
    serializeOne() {
      let len = this.fNumber.length;
      if (len == 3 || len == 7) {
        this.fNumber = this.fNumber + "-";
      }
    },
    serializeTwo() {
      let len = this.sNumber.length;
      if (len == 3 || len == 7) {
        this.sNumber = this.sNumber + "-";
      }
    },
    loadReviews() {
      let el = document.getElementById("reviews");
      el.classList.add("slide-in");
      if (this.rIndex < 23) {
        this.reviewsToDisplay = [];
        for (let i = this.rIndex; i < this.rIndex + 8; i++) {
          this.reviewsToDisplay.push(this.reviews[i]);
        }
      }
      this.rIndex = this.rIndex + 7;
    },
    goBack() {
      this.rIndex = 0;
      this.loadReviews();
    }
  }
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Lato:wght@300;400;700;900&display=swap");
@import url("https://use.typekit.net/sml7caq.css");
#app {
  font-family: "Lato", sans-serif;
}
.hero-banner {
  width: 100%;
  height: 375px;
  background: rgb(255, 211, 54);
  background-image: url("assets/Artboard.svg");
  background-position: center;
  .download {
    padding-top: 30px;
    font-size: 54px;
    font-family: "omnes-pro", sans-serif;
    text-align: center;
    color: #262626;
    letter-spacing: 0px;
  }
  .saving {
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
      margin-right: 45px;
    }
    .right-section {
      margin-left: 45px;
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
        font: normal normal normal 20px/32px Lato;
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
        .input-group-text {
          background-color: #fff !important;
          padding-right: 5px;
          border-right: none !important;
        }
        .form-control {
          outline: none !important;
          padding: 20px 0.75rem !important;
          border-left: none !important;
          letter-spacing: 0px !important;
          color: #b33cc8 !important;
          box-shadow: none;
        }
        .form-control:focus {
          margin-left: -28px !important;
          border-color: #b33cc8 !important;
          border-left: 1px solid #b33cc8 !important ;
          border-radius: 0.25rem !important;
          box-shadow: 0 0 5px #b33cc8;
        }
        .get-app-btn {
          color: #fff;
          margin-top: 20px;
          width: 171px;
          height: 40px;
          background: #b33cc8 0% 0% no-repeat padding-box;
          border-radius: 28px;
          opacity: 1;
          border: none;
          outline: none;
        }
        .get-app-btn:hover {
          color: #b33cc8;
          background: #fff 0% 0% no-repeat padding-box;
          border: 1px solid #b33cc8;
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
    margin-top: 70px;
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
    height: 978px;
    background: #fef8e6 0% 0% no-repeat padding-box;
    .title {
      padding-top: 53px;
      font: normal normal 600 20px/24px omnes-pro;
      letter-spacing: 2px;
      color: #262626;
      text-transform: uppercase;
      opacity: 1;
      border-bottom: 3px solid #b33cc8;
      width: 233px;
      margin-left: auto;
      margin-right: auto;
      line-height: 30px;
    }
    .reviews-container {
      margin-top: 50px;
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      width: 1300px;
    }
    .read-more {
      margin-top: 20px;
      display: flex;
      justify-content: center;
      align-items: center;
    }
    .read-more-btn {
      outline: none;
      background: #b33cc8 0% 0% no-repeat padding-box;
      border-radius: 28px;
      opacity: 1;
      width: 228px;
      height: 40px;
      border: none;
      color: #fff;
    }
    .read-more-btn:hover {
      color: #b33cc8;
      background: #fef8e6 0% 0% no-repeat padding-box;
      border: 1px solid #b33cc8;
    }
  }
}
.app-perks-section {
  width: 1300px;
  margin-left: auto;
  margin-right: auto;
  .title {
    padding-top: 25px;
    font: normal normal 600 20px/24px omnes-pro;
    letter-spacing: 2px;
    color: #262626;
    text-transform: uppercase;
    opacity: 1;
    border-bottom: 3px solid #b33cc8;
    width: 258px;
    margin-left: auto;
    margin-right: auto;
    line-height: 30px;
  }
  .screens-container {
    margin: 60px;
    margin-bottom: 0px;
    display: flex;
    justify-content: center;
    .single-screen {
      margin: 0px 15px;
      .benefit-title {
        text-align: center;
        font: normal normal bold 16px/20px Lato;
        letter-spacing: 0px;
        color: #262626;
      }
      .description {
        margin-top: 8px;
        text-align: center;
        font: normal normal normal 17px/20px Lato;
        letter-spacing: 0px;
        color: #262626;
        width: 280px;
      }
      .screen {
        width: 268px;
        height: 282px;
        opacity: 1;
      }
    }
  }
}
.footer-cotainer {
  height: 242px;
  background: #b33cc8 0% 0% no-repeat padding-box;
  opacity: 1;
  width: 100%;
  .footer-content {
    width: 1325px;
    margin-left: auto;
    margin-right: auto;
    padding: 60px 200px;
    padding-bottom: 0px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    .left {
      text-align: center;
      .heading {
        font: normal normal normal 32px/36px omnes-pro;
        letter-spacing: 0px;
        color: #ffc700;
        opacity: 1;
      }
      .save {
        margin-top: 10px;
        font: normal normal bold 20px/24px Lato;
        letter-spacing: 0px;
        color: #ffffff;
        opacity: 1;
      }
      .download-app {
        margin-top: 40px;
        img {
          margin-left: 7px;
          margin-right: 7px;
        }
      }
    }
    .right {
      span {
        display: block;
        margin-bottom: 12px;
        color: #ffffff;
        font: normal normal bold 18px/30px Lato;
        letter-spacing: 0px;
        color: #ffffff;
        opacity: 1;
      }
      button {
        margin-top: 20px;
        width: 171px;
        height: 40px;
        background: #ffc700 0% 0% no-repeat padding-box;
        border-radius: 28px;
        opacity: 1;
        border: none;
        outline: none;
      }
      button:hover {
        color: #fff;
        background: #b33cc8 0% 0% no-repeat padding-box;
        border: 1px solid #fff;
      }
      .input-group-text {
        background-color: #fff !important;
        padding-right: 0px;
        margin-left: -25px;
        padding-left: 25px;
        border: none !important;
      }
      .form-control {
        outline: none !important;
        padding: 20px 3.5rem !important;
        padding-left: 0.75rem !important;
        border-left: none !important;
        letter-spacing: 0px !important;
        color: #b33cc8 !important;
        // color: #b2b2b2 !important;
        box-shadow: none;
        border: none !important;
      }
      .form-control:focus {
        border-color: #fff !important;
        box-shadow: none !important;
      }
    }
  }
}
.slide-in {
  animation: slide-in 0.5s forwards;
  -webkit-animation: slide-in 0.5s forwards;
}
@keyframes slide-in {
  0% {
    -webkit-transform: translateX(100%);
  }
  100% {
    -webkit-transform: translateX(0%);
  }
}
@-webkit-keyframes slide-in {
  0% {
    transform: translateX(100%);
  }
  100% {
    transform: translateX(0%);
  }
}
</style>
