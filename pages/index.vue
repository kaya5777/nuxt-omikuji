<template>
  <section class="container">
    <div>
      <app-logo/>
      <h1 class="title">
        おみくじ
      </h1>
      <h2 class="subtitle">
        Nuxt.js project
      </h2>
      <button v-on:click="doOmikuji">おみくじを引く</button>
      <h1 class="result"> {{ omikuji }} </h1>
    </div>
  </section>
</template>

<script>
import AppLogo from '~/components/AppLogo.vue'

export default {
  data: function() {
    return {
      omikujilist: ["大吉", "中吉", "吉", "末吉", "凶", "大凶"],
      omikuji: ""
    }
  },
  components: {
    AppLogo
  },
  methods: {
    doOmikuji: function () {
      this.omikuji = this.omikujilist[Math.floor(Math.random() * this.omikujilist.length)]
    }
  }
}
</script>

<style>
.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; /* 1 */
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.result {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; /* 1 */
  display: block;
  font-weight: 300;
  font-size: 120px;
  color: #35495e;
  letter-spacing: 1px;
}
</style>

