<template>
  <div id="app">
    <div id="header">
      <router-link to="/"
        ><img src="./assets/site-logo.png" class="site-logo"
      /></router-link>
      <HeaderSlider />
    </div>
    <router-view />
    <!-- <div class="back-to-top-todo"></div> -->
    <Footer />
  </div>
</template>

<script>
import HeaderSlider from "@/components/header-slider.vue";
import Footer from "@/components/footer.vue";

export default {
  components: {
    HeaderSlider,
    Footer
  }
};
</script>

<style lang="scss">
* {
  font-family: "游ゴシック体", "Yu Gothic", YuGothic, "ヒラギノ角ゴシック Pro",
    "Hiragino Kaku Gothic Pro", "メイリオ", Meiryo, Osaka, "ＭＳ Ｐゴシック",
    "MS PGothic", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

body {
  margin: 0;
  padding: 0;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}

#header {
  .site-logo {
    display: block;
    margin: auto;
    padding: 26px;
  }
}
</style>
