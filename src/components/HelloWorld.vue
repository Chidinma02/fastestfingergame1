<template>
  <div class="hello container">
    <div class="pt-5">
      <!-- <h1>Fastest Finger</h1> -->
      <ProgameHeader></ProgameHeader>
    </div>
    <div class="row vertical-center center in-middle">
      <div class="col-6">
        <!-- <b-button variant="success btn-lg" class="gt">Start</b-button> -->
        <!-- <button type="button" class="btn btn-success btn-lg">Start</button> -->
        <butt></butt>
      </div>
      <div class="col-6">
        <!-- <b-button variant="light btn-lg" class="gt">Rules</b-button> -->
        <div class="button-container-3">
          <span class="mas">Rules</span>
          <button type="button" name="Hover" class="j" @click="goToHome()">
            Rules
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import butt from "@/components/butt.vue";
import ProgameHeader from "@/components/header.vue";
export default {
  name: "HelloWorld",
  components: {
    butt,
    ProgameHeader,
  },
  data() {
    return {};
  },
  methods: {
    goToHome() {
      this.$router.push("/about");
    },
  },
};
</script>

<style lang="scss" scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.gt {
  background-color: white !important;
}
.vertical-center {
  /* margin: 0;
  position: absolute;
  top: 50%;
  left: 40%;
  -ms-transform: translateY(-50%);
  transform: translateY(-50%);
  text-align: center !important;*/
}
.in-middle {
  width: 100%;
  margin-top: 15%;
}
.container {
}

@mixin button($bcolor, $url, $x1, $y1, $bor, $col) {
  background: $bcolor;
  -webkit-mask: url($url);
  mask: url($url);
  -webkit-mask-size: $x1 $y1;
  mask-size: $x1 $y1;
  border: $bor;
  color: $col;
}

.header {
  text-align: center;
  font-family: "Roboto", sans-serif;
  font-size: 34px;
  margin-top: 12vh;
}

.footer {
  text-align: center;
  font-family: "Lato", sans-serif;
  font-weight: 300;
  font-size: 20px;
  margin-top: 15vh;
}

.button-container-1 {
  position: relative;
  width: 100px;
  height: 50px;
  margin-left: auto;
  margin-right: auto;
  margin-top: 6vh;
  overflow: hidden;
  border: 1px solid #157347;
  font-family: "Lato", sans-serif;
  font-weight: 300;
  font-size: 20px;
  transition: 0.5s;
  letter-spacing: 1px;
  border-radius: 8px;

  button {
    width: 101%;
    height: 100%;
    font-family: "Lato", sans-serif;
    font-weight: 300;
    font-size: 20px;
    letter-spacing: 1px;
    font-weight: bold;

    @include button(
      #157347,
      "https://raw.githubusercontent.com/robin-dela/css-mask-animation/master/img/nature-sprite.png",
      2300%,
      100%,
      none,
      #fff
    );
    cursor: pointer;
    -webkit-animation: ani2 0.7s steps(22) forwards;
    animation: ani2 0.7s steps(22) forwards;

    &:hover {
      -webkit-animation: ani 0.7s steps(22) forwards;
      animation: ani 0.7s steps(22) forwards;
    }
  }
}

.button-container-2 {
  position: relative;
  width: 100px;
  height: 50px;
  margin-left: auto;
  margin-right: auto;
  margin-top: 7vh;
  overflow: hidden;
  border: 1px solid #157347;
  font-family: "Lato", sans-serif;
  font-weight: 300;
  transition: 0.5s;
  letter-spacing: 1px;
  border-radius: 8px;

  button {
    width: 101%;
    height: 100%;
    font-family: "Lato", sans-serif;
    font-weight: 300;
    font-size: 11px;
    letter-spacing: 1px;
    font-weight: bold;

    @include button(
      #157347,
      "https://raw.githubusercontent.com/robin-dela/css-mask-animation/master/img/urban-sprite.png",
      3000%,
      100%,
      none,
      #fff
    );
    cursor: pointer;
    -webkit-animation: ani2 0.7s steps(29) forwards;
    animation: ani2 0.7s steps(29) forwards;

    &:hover {
      -webkit-animation: ani 0.7s steps(29) forwards;
      animation: ani 0.7s steps(29) forwards;
    }
  }
}

.mas {
  position: absolute;
  color: #157347;
  text-align: center;
  width: 101%;
  font-family: "Lato", sans-serif;
  font-weight: 300;
  position: absolute;
  font-size: 11px;
  margin-top: 17px;
  overflow: hidden;
  font-weight: bold;
}

@-webkit-keyframes ani {
  from {
    -webkit-mask-position: 0 0;
    mask-position: 0 0;
  }

  to {
    -webkit-mask-position: 100% 0;
    mask-position: 100% 0;
  }
}

@keyframes ani {
  from {
    -webkit-mask-position: 0 0;
    mask-position: 0 0;
  }

  to {
    -webkit-mask-position: 100% 0;
    mask-position: 100% 0;
  }
}

@-webkit-keyframes ani2 {
  from {
    -webkit-mask-position: 100% 0;
    mask-position: 100% 0;
  }

  to {
    -webkit-mask-position: 0 0;
    mask-position: 0 0;
  }
}

@keyframes ani2 {
  from {
    -webkit-mask-position: 100% 0;
    mask-position: 100% 0;
  }

  to {
    -webkit-mask-position: 0 0;
    mask-position: 0 0;
  }
}

a {
  color: #00ff95;
}

.button-container-3 {
  position: relative;
  width: 100px;
  height: 50px;
  margin-left: auto;
  margin-right: auto;
  margin-top: 8vh;
  overflow: hidden;
  border: 1px solid #157347;
  font-family: "Lato", sans-serif;
  font-weight: 300;
  transition: 0.5s;
  letter-spacing: 1px;
  border-radius: 8px;

  button {
    width: 101%;
    height: 100%;
    font-family: "Lato", sans-serif;
    font-weight: 300;
    font-size: 11px;
    letter-spacing: 1px;
    font-weight: bold;

    @include button(
      #157347,
      "https://raw.githubusercontent.com/pizza3/asset/master/natureSmaller.png",
      7100%,
      100%,
      none,
      #fff
    );
    cursor: pointer;
    -webkit-animation: ani2 0.7s steps(70) forwards;
    animation: ani2 0.7s steps(70) forwards;

    &:hover {
      -webkit-animation: ani 0.7s steps(70) forwards;
      animation: ani 0.7s steps(70) forwards;
    }
  }
}
.j {
  font-size: 20px !important;
}
</style>