<script>
export default {};
</script>

<template>
  <div id="shop">
    <div class="container">
        <div class="text">
            <p>
            <span>13.32</span>
            who seeks after it and<br />
            wants to have it
            </p>
        </div>
    </div>
    <div class="box">
        <div class="container">
            <p>Neque porro quisquam<br>est qui dolorem!</p>
            <img class="mt-4" src="/test/src/assets/image/market.svg" alt="market">
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "../assets/style/style.scss";
#shop {
  background-color: $bg;
  padding-top: 80px;
  .text {
    position: relative;
    z-index: 0;
    padding-bottom: 350px;
    &:after {
      content: "";
      position: absolute;
      left: 50%;
      bottom: 100px;
      transform: translateX(-50%);
      width: 200px;
      height: 200px;
      object-fit: contain;
      background: url(/test/src/assets/image/lighthouse.svg) no-repeat center/contain;
    }
    p {
      width: fit-content;
      margin: auto;
      text-align: center;
      color: $primary-color;
      font-weight: 700;
      font-size: 20px;
      line-height: 140%;
      position: relative;
      z-index: 0;
      span {
        display: block;
        color: $default-color;
      }
      &:after {
        content: "";
        position: absolute;
        left: -24px;
        transform: rotate(-20deg);
        top: 0;
        bottom: 0;
        width: 1px;
        z-index: -1;
        background-color: $primary-color;
      }
      &:before {
        content: "";
        position: absolute;
        right: -24px;
        transform: rotate(20deg);
        top: 0;
        bottom: 0;
        width: 1px;
        z-index: -1;
        background-color: $primary-color;
      }
    }
  }
  .box {
    border-radius: 50px 50px 0px 0px;
    background: $primary-color;
    color: #fff;
    text-align: center;
    padding-bottom: 30px;
    p {
      letter-spacing: 0.2em;
      font-weight: 700;
      font-size: 20px;
      line-height: 200%;
    }
  }
}
</style>
