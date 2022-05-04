<template>
  <div class="container">
    <div>
      <!-- <input @click="modalShow = !modalShow" /> -->

      <b-modal>Hello From Modal!</b-modal>
      <b-modal
        id="bv-modal-example"
        centered
        title="BootstrapVue"
        v-model="modalShow"
        hide-footer
        hide-header
        no-close-on-backdrop
      >
        <template #modal-title>oops You lost </template>
        <div class="d-block text-center">
          <h3 class="mt-3 mb-3">Game Over!</h3>
          <h5 class="mb-3">your score {{ count }}</h5>
        </div>
        <div class="row mb-4 mb-3">
          <div class="col-6 text-center">
            <button class="btn btn-lg btn-danger" @click="quit()">quit</button>
          </div>
          <div class="col-6 text-center">
            <button class="btn btn-lg btn-success" @click="again()">
              play again
            </button>
          </div>
        </div>
        <!-- <b-button class="mt-3" block @click="$bvModal.hide('bv-modal-example')" -->
        <!-- >Close Me</b-button -->
      </b-modal>
    </div>
    <div class="pt-5">
      <h1>Fastest Finger</h1>
      <p></p>
    </div>
    <div class="row">
      <div class="col-6 offset-3">Type the given word</div>
      <div class="col-6 offset-3 mt-3">
        <h3 class="mb-5">{{ text }}</h3>
        <!-- <li v-for="word in words" :key="word">{{ word }}</li> -->
        <input
          type="email"
          class="form-control"
          id="exampleInputEmail1"
          aria-describedby="emailHelp"
          placeholder="Enter given word"
          v-model="letter"
          @change.prevent="linking()"
        />
      </div>
    </div>
    <div class="row mt-5 pt-5">
      <div class="col">
        <h3>Countdown Timer:{{ timerCount }}</h3>
      </div>
      <div class="col">
        <div>
          <h3>Score:{{ count }}</h3>
          <h3>{{ minus }}</h3>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProgameType",

  data() {
    return {
      modalShow: false,
      addon: false,
      timerCount: 20,
      count: 0,
      text: "",
      // randomIndex: 0,

      words: [
        "brain",
        "brand",
        "bread",
        "sugar",
        "event",
        "occupation",
        "dozen",
        "depth",
        "eager",
        "enemy",
        "fight",
        "fixed",
        "forum",
        "grace",
        "crown",
        "japan",
        "Jones",
        "magic",
        "march",
        "media",
        "pitch",
        "plane",
        "quiet",

        "party",
        "prior",
        "radio",
        "ratio",
        "rapid",
        "serve",
        "shock",
        "shown",
        "suite",
        "steam",
        "stand",
        "theme",
        "throw",
        "thick",
        "union",
        "waste",
        "wheel",
        "watch",
        "visit",
        "wound",
        "youth",
        "worthy",
        "youth",
      ],
      letter: "",
      minus: "",
    };
  },

  mounted() {
    this.chooseRandomFromArray();

    const timer = setInterval(() => {
      this.timerCount--;
      if (this.timerCount === 0) {
        this.linking();
        clearInterval(timer);
      }
    }, 2000);

    this.OpenBootstrapPopup();
  },

  methods: {
    OpenBootstrapPopup() {
      this.$refs.input.modal("show");
    },
    // This method chooses a random word from the array
    chooseRandomFromArray() {
      // selects a random number btw 0 and the length of the
      // words array
      let randomIndex = Math.floor(Math.random() * this.words.length);

      // uses the random number to get a word from the words
      // array and assigns this word to the text dat
      this.text = this.words[randomIndex];
    },
    linking() {
      if (this.text == this.letter) {
        // this.$store.dispatch('addFavoriteStore', payload)
        this.count = this.count + 1;
        this.letter = "";
        this.chooseRandomFromArray();
        // console.log("li");
        // return true;
      } else if (this.text !== this.letter) {
        // this.$store.dispatch('deleteFavoriteStore', payload)
        // return false;
        this.addon = true;
        this.showmode();
        // this.minus = "game over";
      }
    },

    showmode() {
      this.modalShow = !this.modalShow;
    },
    quit() {
      this.$router.push("/");
    },
    again() {
      // this.$router.push("/home");
      this.letter = "";
      // this.timer();
      this.linking();
      this.chooseRandomFromArray();
      this.count = 0;
    },

    //
  },
};
</script>

<style lang="scss" scoped></style>