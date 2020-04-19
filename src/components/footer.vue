<template>
  <div id="footer">
    <div class="footer-wrap">
      <router-link to="/other">
        <span>運営会社</span><span>個人情報保護について</span></router-link
      >
      <p>©2016 Sample</p>
    </div>
    <go-top
      bg-color="rgba(0,0,0,0.5);"
      fg-color="#000"
      box-shadow="none"
    ></go-top>
  </div>
</template>

<script>
import GoTop from "@inotom/vue-go-top";

export default {
  name: "Footer",
  components: {
    GoTop
  }
};
</script>

<style lang="scss" scoped>
#footer {
  background-color: #000;
  color: #fff;
  padding: 10px;
  margin-top: 80px;

  .footer-wrap {
    width: 90%;
    display: block;
    margin: auto;
  }

  a {
    text-decoration: none;
    color: #fff;
    float: left;
    font-size: 13px;

    &:visited {
      text-decoration: none;
      color: #fff;
    }

    span {
      &:last-child {
        margin-left: 20px;
      }
    }
  }

  p {
    margin: 0;
    float: right;
    font-size: 14px;
  }

  &::after {
    content: "";
    clear: both;
    display: table;
  }
}
</style>
