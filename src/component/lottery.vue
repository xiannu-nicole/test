<script>
export default {
  data() {
    return {
      lottery: [
        {
          id: "A",
          gift: "dehumidifier",
          num: "one",
        },
        {
          id: "B",
          gift: "range hood",
          num: "one",
        },
        {
          id: "C",
          gift: "vacuum cleaner",
          num: "one",
        },
        {
          id: "D",
          gift: "toaster",
          num: "one",
        },
        {
          id: "E",
          gift: "scale",
          num: "one",
        },
        {
          id: "F",
          gift: "straightening iron",
          num: "one",
        },
        {
          id: "G",
          gift: "vacuum cleaner",
          num: "one",
        },
        {
          id: "H",
          gift: "rice cooker",
          num: "one",
        },
      ],
    };
  },
};
</script>

<template>
  <div id="lottery">
    <div class="container">
      <div class="row gy-5 gx-3 gx-lg-5">
        <div
          class="col-6 col-md-4 box-wrapper"
          v-for="item in lottery"
          :key="item.id"
        >
          <div class="box">
            <strong>{{ item.id }}</strong>
            <div class="d-flex justify-content-end">
            <small>{{ item.num }}</small>
          </div>
              <h5>{{ item.gift }}</h5>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "../assets/style/style.scss";
#lottery {
  background-color: $bg;
}
.box-wrapper {
    .box {
      background: #ffffff;
      box-shadow: 0px 8px 0px #edeef0;
      border-radius: 20px;
      padding-bottom: 20px;
    strong{
        display: inline-block;
        position: relative;
        left: 50%;
        transform: translateX(-50%);
        text-align: center;
        font-size: 16px;
line-height: 125%;
color: #fff;
z-index: 0;
&:after{
    content: "";
    z-index: -1;
    position: absolute;
    left: -30px;
    right: -30px;
    top: -30px;
    bottom: -30px;
    background-image: url(/test/src/assets/image/certificateD.svg);
    background-size: contain;
    background-repeat: no-repeat;
    background-position: center;
}
    }
    h5 {
        text-align: center;
      font-weight: 700;
      font-size: 18px;
      line-height: 125%;
      color: #a0bcc8;
      margin-top: 20px;
    }
    small{
        display: inline-block;
        width: fit-content;
        color: #a0bcc8;
        font-size: 12px;
        line-height: 140%;
padding: 3px 10px;
background: #FAFAFA;
border: 1px solid #a0bcc8;
border-radius: 50px;
margin: 0 12px;


    }
  }
  &:nth-child(1),
  &:nth-child(2),
  &:nth-child(3) {
    .box {
        strong{
            &:after{
    background-image: url(/test/src/assets/image/certificateA.svg);
    bottom: -40px;
}
        }
      h5 {
        color: #b3b960;
        z-index: 0;
      }
      small{
        color: #b3b960;
border: 1px solid #b3b960;
      }
    }
  }
}
</style>
