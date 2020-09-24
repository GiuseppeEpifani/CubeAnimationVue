<template >
  <div class="container">
    <div class="cont-children">
      <img class="main" v-bind:src="this.mainComponent" alt="" />
      <div class="side front">
        <div class="box">
          <img v-bind:src="this.frontComponent" alt="" />
        </div>
      </div>

      <div class="side right">
        <div class="box">
          <img v-bind:src="this.rightComponent" alt="" />
        </div>
      </div>

      <div class="side left">
        <div class="box">
          <img v-bind:src="this.leftComponent" alt="" />
        </div>
      </div>

      <div class="side back">
        <div class="box">
          <img v-bind:src="this.backComponent" alt="" />
        </div>
      </div>

      <div
        class="side down"
        v-bind:style="{ backgroundColor: this.color }"
      ></div>
      <div class="side shadow"></div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["main", "front", "right", "left", "back", "color"],
  data() {
    return {
      mainComponent: this.main,
      frontComponent: this.front,
      rightComponent: this.right,
      leftComponent: this.left,
      backComponent: this.back,
      colorComponnet: this.color,
    };
  },
};
</script>

<style scoped>
.body {
  background-color: #ccc;
}
.container {
  height: 400px;
  width: 400px;
  perspective: 1000px;
  margin: 160px auto;
  cursor: pointer;
}

.cont-children {
  height: 300px;
  width: 300px;
  transform-style: preserve-3d;
  animation: rotar 13s infinite linear;
}

.side {
  position: absolute;
  transform-style: preserve-3d;
  height: 100%;
  width: 100%;
}

.box {
  height: 100%;
  width: 100%;
  transition: 1.5s;
  transform-origin: bottom;
}
.box img {
  height: 100%;
  width: 100%;
}
.front {
  transform: rotateY(0deg) translateZ(150px);
}

.right {
  transform: rotateY(90deg) translateZ(150px);
}
.left {
  transform: rotateY(-90deg) translateZ(150px);
}
.back {
  transform: rotateY(180deg) translateZ(150px);
}
.down {
  transform: rotateX(-90deg) translateZ(150px);
}

.shadow {
  transform: rotateX(-90deg) translateZ(230px);
  background-color: #333;
}

.cont-children:hover .box {
  transform: rotateX(-80deg);
}

.main {
  width: 62.5%;
  height: 62.5%;
  position: absolute;
  transform: translate(-50%, -50%);
  left: 50%;
  top: 50%;
  border-radius: 20%;
}

@media only screen and (max-width: 900px) {
  .container {
    height: 300px;
    width: 300px;
    perspective: 1000px;
    margin: 120px auto;
    cursor: pointer;
  }

  .cont-children {
    height: 225px;
    width: 225px;
    transform-style: preserve-3d;
    animation: rotar 13s infinite linear;
  }

  .front {
    transform: rotateY(0deg) translateZ(112.5px);
  }

  .right {
    transform: rotateY(90deg) translateZ(112.5px);
  }
  .left {
    transform: rotateY(-90deg) translateZ(112.5px);
  }
  .back {
    transform: rotateY(180deg) translateZ(112.5px);
  }
  .down {
    transform: rotateX(-90deg) translateZ(112.5px);
  }

  .shadow {
    transform: rotateX(-90deg) translateZ(172.5px);
    background-color: #333;
  }
}

@media only screen and (max-width: 700px) {
  .container {
    height: 200px;
    width: 200px;
    perspective: 1000px;
    margin: 80px auto;
    cursor: pointer;
  }

  .cont-children {
    height: 150px;
    width: 150px;
    transform-style: preserve-3d;
    animation: rotar 13s infinite linear;
  }

  .front {
    transform: rotateY(0deg) translateZ(75px);
  }

  .right {
    transform: rotateY(90deg) translateZ(75px);
  }
  .left {
    transform: rotateY(-90deg) translateZ(75px);
  }
  .back {
    transform: rotateY(180deg) translateZ(75px);
  }
  .down {
    transform: rotateX(-90deg) translateZ(75px);
  }

  .shadow {
    transform: rotateX(-90deg) translateZ(115px);
    background-color: #333;
  }
}

@media only screen and (max-width: 400px) {
  .container {
    height: 100px;
    width: 100px;
    perspective: 1000px;
    margin: 120px auto;
    cursor: pointer;
  }

  .cont-children {
    height: 75px;
    width: 75px;
    transform-style: preserve-3d;
    animation: rotar 13s infinite linear;
  }

  .front {
    transform: rotateY(0deg) translateZ(37.5px);
  }

  .right {
    transform: rotateY(90deg) translateZ(37.5px);
  }
  .left {
    transform: rotateY(-90deg) translateZ(37.5px);
  }
  .back {
    transform: rotateY(180deg) translateZ(37.5px);
  }
  .down {
    transform: rotateX(-90deg) translateZ(37.5px);
  }

  .shadow {
    transform: rotateX(-90deg) translateZ(57.5px);
    background-color: #333;
  }
}

@keyframes rotar {
  0% {
    transform: rotateY(0deg);
  }
  100% {
    transform: rotateY(360deg);
  }
}
</style>
