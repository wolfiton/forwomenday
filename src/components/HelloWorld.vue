<template>
  <section class="hero is-info">
    <div class="hero-body">
      <div class="container">
        <h1 class="title">
          For Women Day
        </h1>
        <h2 class="subtitle has-text-weight-semibold">
          Would you like to introduce yourself? becauese I would like to wish
          you a happy birthday
        </h2>

        <b-field label="Username" class="has-text-white has-text-center">
          <b-input v-model="username" class="has-text-centered" placeholder="Nickname"></b-input>
        </b-field>
        <p
          class="is-size-1 has-text-weight-semibold"
          v-if="setUsername.length > 2"
        >
          Happy Birthday to you {{ setUsername }}!
        </p>
        <div v-if="setUsername.length > 2">
          <h2 class="subtitle has-text-weight-semibold">
            I also prepared a gif for you <span class="is-size-1 has-text-weight-semibold">
            <i class="fas fa-gift has-text-warning"></i>
          </span>
          </h2>
          

          <div class="block has-text-warning">
            <b-radio v-model="radio" name="name" native-value="flower">
              <span class="is-size-1 has-text-weight-semibold">
            <i class="fas fa-gift"></i>
          </span>
              <strong class="has-text-white">Gift 1</strong>
            </b-radio>
            <b-radio v-model="radio" name="name" native-value="cake">
              <span class="is-size-1 has-text-weight-semibold">
            <i class="fas fa-gift"></i>
          </span>
              <strong class="has-text-white">Gift 2</strong>
            </b-radio>
            <b-radio v-model="radio" name="name" native-value="ladybug">
              <span class="is-size-1 has-text-weight-semibold">
            <i class="fas fa-gift"></i>
          </span>
              <strong class="has-text-white">Gift 3</strong>
            </b-radio>
          </div>
          <p class="content">
            <b>You choose the</b>
            <b> {{ setGift }} </b>
          </p>

          <div>
            <span v-if="setGift === 'flower'">
              <img
                class="image-style"
                src="@/assets/images/flower.jpg"
                alt=""
              />
              <p class="is-size-1 has-text-weight-semibold">
                May the sun light your path
              </p>
            </span>
            <span v-else-if="setGift === 'cake'">
              <img class="image-style" src="@/assets/images/cake.jpg" alt="" />
              <p class="is-size-1 has-text-weight-semibold">
                May this cake make your life sweater
              </p>
            </span>
            <span v-else-if="setGift === 'ladybug'">
              <img
                class="image-style"
                src="@/assets/images/ladybug.jpg"
                alt=""
              />
              <p class="is-size-1 has-text-weight-semibold">
                May the Ladybug bring you luck and fortune
              </p>
            </span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "HelloWorld",

  props: {
    msg: String
  },
  data() {
    return {
      username: "",
      radio: ""
    };
  },
  computed: {
    setUsername() {
      return this.username.toUpperCase();
    },

    setGift() {
      return this.radio;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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

.image-style {
  height: 400px;
  width: 400px;
}
</style>
