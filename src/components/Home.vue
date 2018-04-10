<template>
  <div id="main-page">
    <div id="particle-container">
      <div class="particle" v-for="n in 50" :key="n"></div>
    </div>
    <div class="invitation">
      <img src="~assets/images/circular-flowers.svg">
      <div class="invitation-text">
        <div class="invitation-name">Herri & Anin</div>
        <div class="invitation-date">xx xxxx xxxx</div>
      </div>
      <div class="invitation-title">save the date</div>
    </div>
  </div>
</template>

<script src="./js/home.js"></script>
<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css?family=Clicker+Script');
#main-page {
  background: #00A7E1;
  position: fixed;
  width: 100%;
  height: 100%;
  left: 0;
  font-family: 'Clicker Script', cursive;
  top: 0;
  .invitation {
    width: 100%;
    max-width: 80%;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    font-size: 30px;
    color: #fff;
    &-text {
      width: 100%;
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
    }
    img {
      width: 100%;
      opacity: 0.8;
    }
  }
}
.particle {
  position: absolute;
  border-radius: 50%;
}

@for $i from 1 through 50 {
  @keyframes particle-animation-#{$i} {
    100% {
        transform: translate3d((random(90) * 1vw), (random(90) * 1vh), (random(100) * 1px));
    }
  }
  .particle:nth-child(#{$i}){
    animation: particle-animation-#{$i} 30s infinite;
    $size: random(3) + 5 + px;
    opacity: random(70)/100;
    height: $size;
    width: $size;
    animation-delay: -$i * .2s;
    transform: translate3d((random(90) * 1vw), (random(90) * 1vh), (random(100) * 1px));
    background: #fff;
  }
}
</style>
