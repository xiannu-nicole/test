<script>
export default {
  data() {
    return {
      stores: ["store1", "store2", "store3", "store4", "store5"],
      store: "",
      storeSituation: "",
      name: "",
      nameSituation: "",
      phone: "",
      phoneSituation: "",
      amount: "",
      amountSituation: "",
      pays: ["digital payment", "ATM"],
      pay: "",
      paySituation: "",

      submit:true,
      submitFailure:false,
      submitSuccess:false,
    };
  },

  watch: {

    store(value) {
    this.submit = true,
      this.submitFailure = false;
      this.submitSuccess = false;
      if (value === "") {
        this.storeSituation = "wrong";
      } else {
        this.storeSituation = "";
      }
    },
    name() {
    this.submit = true,
      this.submitFailure = false;
      this.submitSuccess = false;
      if (/[^\u4e00-\u9fa5a-zA-Z]/.test(this.name)) {
        this.nameSituation = "wrong";
      } else {
        this.nameSituation = "";
      }
    },
    phone() {
    this.submit = true,
      this.submitFailure = false;
      this.submitSuccess = false;
      if (!/\d/.test(this.phone) || this.phone.length !== 10) {
        this.phoneSituation = "wrong";
      } else {
        this.phoneSituation = "";
      }
    },
    amount() {
    this.submit = true,
      this.submitFailure = false;
      this.submitSuccess = false;
      if (!/\d/.test(this.amount) || Number(this.amount) <= 0) {
        this.amountSituation = "wrong";
      } else {
        this.amountSituation = "";
      }
    },
    pay(value) {
    this.submit = true,
      this.submitFailure = false;
      this.submitSuccess = false;
      if (value === "") {
        this.paySituation = "wrong";
      } else {
        this.paySituation = "";
      }
    },
  },

  methods: {
    getSubmitResult() {
      if (
        this.store !== ""  &&
        this.nameSituation !== "wrong" &&
        this.name !== "" && 
        this.phoneSituation !== "wrong" &&
        this.phone !== "" &&
        this.amountSituation !== "wrong" &&
        this.amount !== "" &&
        this.pay !== "" 

      ){
        this.submitSuccess = true;
      }
      else{
        this.submitFailure = true;
      }
    },
  },
};
</script>

<template>
  <div id="form">
    <div class="container">
      <h5>FORM</h5>
      <div class="box">
        <div class="mb-5">
          <h6>store <span class="need">*</span></h6>
          <select :class="storeSituation" v-model="store">
            <option selected disabled value="">請選擇</option>
            <option v-for="item in stores" :value="item" :key="item">
              {{ item }}
            </option>
          </select>
        </div>
        <div class="mb-5">
          <h6>name <span class="need">*</span></h6>
          <input
            type="text"
            :class="nameSituation"
            placeholder="請輸入姓名"
            v-model="name"
          />
        </div>
        <div class="mb-5">
          <h6>phone <span class="need">*</span></h6>
          <input
            type="text"
            :class="phoneSituation"
            placeholder="請輸入電話"
            v-model="phone"
          />
        </div>
        <div class="mb-5">
          <h6>Amount of consumption <span class="need">*</span></h6>
          <input
            type="text"
            :class="amountSituation"
            placeholder="請輸入費用"
            v-model="amount"
          />
        </div>
        <div>
          <h6>payment <span class="need">*</span></h6>
          <select :class="paySituation" v-model="pay">
            <option selected disabled value="">請選擇</option>
            <option v-for="item in pays" :value="item" :key="item">
              {{ item }}
            </option>
          </select>
        </div>
      </div>
      <div class="d-flex justify-content-center align-items-center">
        <a @click="[getSubmitResult(),submit = false]" :class="submit === false ? 'hide' : ''" class="form-btn">submit</a>
        <div
          :class="submitSuccess === true ? 'show' : ''"
          class="success-box text-center"
        >
        <a
          class="form-btn success"
        >
          <div class="d-flex align-items-center justify-content-center">
            <img src="/test/src/assets/image/success.svg" class="me-2" alt="" />
            <span>success</span>
          </div>
        </a>
        </div>
        <div
          :class="submitFailure === true ? 'show' : ''"
          class="failure-box text-center"
        >
          <a class="form-btn failure mb-2">
            <div>
              <div class="d-flex align-items-center justify-content-center">
                <img src="/test/src/assets/image/failure.png" class="me-2" alt="" />
                <span>failure</span>
              </div>
            </div>
          </a>
          <small class="d-block" style="color: #e06d6d">This person does not exist</small>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "../assets/style/style.scss";
#form {
  background-color: $bg;
}
h5 {
  color: $default-color;
  letter-spacing: 0.2em;
  line-height: 125%;
  font-size: 18px;
  text-align: center;
  background: #ffffff;
  border: 2px solid $default-color;
  box-shadow: 0px 1px 10px rgba(73, 72, 72, 0.25);
  border-radius: 50px;
  padding: 10px 20px;
  display: inline-block;
  left: 50%;
  transform: translateX(-50%) translateY(62.25%);
  line-height: 125%;
  position: relative;
  z-index: 1;
  &:after {
    content: "";
    position: absolute;
    width: 60px;
    height: 60px;
    top: 50%;
    transform: translateY(-50%);
    background: url(/test/assets/image/turtle.png) no-repeat center/contain;
  }
}

.box {
  color: $primary-color;
  background: #fff;
  border: 2px solid $default-color;
  border-radius: 20px;
  padding: 48px 16px 24px;
  position: relative;
  z-index: 0;
  h6 {
    span.need {
      color: red;
    }
  }
  select {
    appearance: none;
    background: url("/test/src/assets/image/down.png") no-repeat 97% center/11px 7px;
  }
  select,
  input {
    width: 100%;
    padding: 8px 16px;
    border: 1px solid $primary-color;
    border-radius: 20px;
    &.focus {
      border: 1px solid $focus !important;
    }
    &.wrong {
      border: 2px solid $wrong;
    }
  }
}
a.form-btn {
  box-shadow: 0px 4px 10px rgba(40, 35, 35, 0.35),
    0px -4px 10px rgba(255, 255, 255, 0.9);

  &:hover {
    cursor: pointer;
  }
  &:active {
    background: $pressed-color;
  }
}
.failure-box {
    display: none;
    color: #ffe3e3;
    img{
      width: 20px;
      height: 20px;
    }
  }
  .success-box{
    color: #e6ffb1;
    display: none;
    img{
      width: 20px;
      height: 20px;
    }
  }
.show {
  display: block;
}
.hide {
  display: none;
}
</style>
