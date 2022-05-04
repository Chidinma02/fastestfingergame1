<template>
  <div>
    <div class="row">
      <div class="col-9 text-center">
        <div class="">
          <h1>Fastest Finger</h1>
        </div>
      </div>
      <div class="col-3">
        <div class="form-group">
          <label>
            <button
              class="btn btn-primary btn-sm"
              @click.prevent="
                playSound(
                  'https://www.fiftysounds.com/royalty-free-music/most-popular-music.html'
                )
              "
            >
              <span class="fa fa-play-circle-o"></span>
            </button>
            Play Air Plane Ding
          </label>
          <br />
          <label>
            <button
              class="btn btn-primary btn-sm"
              @click.prevent="
                playSound(
                  'http://soundbible.com/mp3/Elevator Ding-SoundBible.com-685385892.mp3'
                )
              "
            >
              <span class="fa fa-play-circle-o"></span>
            </button>
            Play Elevator Ding
          </label>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProgameHeader",

  data() {
    return {
      text: "",
      words: ["Nice,Elaborate,Event,Enjoy", "Occupation"],
    };
  },

  mounted() {},

  methods: {
    playSound(sound) {
      if (sound) {
        var audio = new Audio(sound);
        audio.play();
      }
    },
  },
};
</script>

<style lang="scss" scoped>
.btn {
  outline: none !important;
}
.btn.btn-primary {
  background-color: #5c4084;
  border-color: #5c4084;
  outline: none;
}
.btn.btn-primary:hover {
  background-color: #442f62;
  border-color: #442f62;
}
.btn.btn-primary:active,
.btn.btn-primary:focus {
  background-color: #684895;
  border-color: #684895;
}
.btn.btn-primary .fa {
  padding-right: 4px;
}
.btn-sm {
  font-size: 22px;
  padding: 2px 1px 2px 4px;
  line-height: 12px;
  margin-right: 10px;
}
.form-group {
  margin-bottom: 25px;
}
</style>