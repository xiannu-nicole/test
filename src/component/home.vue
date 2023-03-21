<script>
</script>

<template>
  <div id="home">
    <div class="container">
      <h2>There is no one<br />who loves pain</h2>
      <div class="text-center">
        <a class="form-btn">FORM</a>
      </div>
      <div class="box">
        <div class="bubble-box">
          <img class="bubble" src="/test/assets/image/泡泡.png" alt="" />
          <img class="sup" src="/test/assets/image/sup2.svg" alt="" />
          <img class="board" src="/test/assets/image/船槳.png" alt="" />
        </div>
        <div>
          <h5>paragraph</h5>
          <ol>
            <li>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</li>
          </ol>
        </div>
        <div class="mt-4">
          <h5>paragraph</h5>
          <ol>
            <li>
              Quisque sodales <strong>leo vitae vulputate auctor.</strong>
            </li>
            <li>
              Proin ac justo ut nisl tincidunt imperdiet.Maecenas viverra
              liberoa pellentesque blandit.
            </li>
            <li>
              Cras tristique tellus id leo bibendum, eu dapibus nisl accumsan.
            </li>
            <li>
              Donec ultrices sapien<strong
                >vitae leo venenatis ullamcorper.</strong
              >
            </li>
          </ol>
        </div>
        <div class="fireworks-box">
          <img class="sup" src="/test/assets/image/sup.svg" alt="" />
          <img class="fireworks" src="/test/assets/image/煙火.svg" alt="" />
        </div>
      </div>
    </div>
      <div class="autoplay">
        <img class="wave-bg" src="/test/assets/image/海浪.png" alt="" />
        <img class="wave-bg" src="/test/assets/image/海浪.png" alt="" />
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "../assets/style/style.scss";
#home {
  background-color: $primary-color;
  position: relative;
  z-index: 0;
  overflow-x: hidden;
  &:before {
    content: "";
    position: absolute;
    left: 0;
    right: 0;
    top: 0;
    bottom: 0;
    background: url(/test/assets/image/白色海浪.png) no-repeat center/cover;
    z-index: -1;
  }
.container{
    margin-bottom: 100px;
}
}

h2 {
  color: #fff;
  letter-spacing: 0.2em;
  line-height: 125%;
  font-size: 32px;
  text-align: center;
}

.box {
  color: $primary-color;
  background: $light-bg;
  border: 2px solid $default-color;
  border-radius: 20px;
  padding: 24px 16px;
  position: relative;
  z-index: 0;
  .bubble-box {
    .bubble {
      position: absolute;
      width: 30px;
      height: 30px;
      right: 0px;
      z-index: -2;
      animation: up 1s forwards;
      @keyframes up {
        from {
          top: 10px;
        }
        to {
          top: -60px;
        }
      }
    }
    .board {
      position: absolute;
      width: 60px;
      height: 60px;
      right: -15px;
      top: -25px;
      z-index: -1;
      animation: wave 1s infinite alternate;
      @keyframes wave {
        from {
          transform: rotate(-45deg);
        }
        from {
          transform: rotate(30deg);
        }
      }
    }
    .sup {
      position: absolute;
      width: 60px;
      height: 60px;
      right: -15px;
      top: -25px;
      z-index: -2;
    }
  }

  h5 {
    display: inline-block;
    left: 50%;
    transform: translateX(-50%);
    line-height: 125%;
    margin-bottom: 24px;
    position: relative;
    &:before,
    &:after {
      content: "";
      position: absolute;
      width: 28px;
      height: 28px;
      top: 50%;
      transform: translateY(-50%);
      background: url(/test/assets/image/cactus.png) no-repeat center/contain;
    }
    &:before {
      left: -30px;
    }
    &:after {
      right: -30px;
    }
  }
  ol {
    li {
      strong {
        text-decoration: underline;
      }
    }
  }
  .fireworks-box {
    position: absolute;
    left: 10px;
    bottom: -30px;
    .sup {
      position: absolute;
      left: 0;
      bottom: 0;
      width: 60px;
      height: 60px;
    }
    .fireworks {
      position: absolute;
      left: -20px;
      bottom: -10px;
      width: 60px;
      height: 60px;
      animation: zoom-in 1s forwards;
      @keyframes zoom-in {
        from {
          transform: scale(0);
          opacity: 1;
        }
        to {
          transform: scale(1.5);
          opacity: 0.2;
        }
      }
    }
  }
}
</style>
