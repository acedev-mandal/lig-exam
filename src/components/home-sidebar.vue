<template>
  <div class="side-bar">
    <div class="dummy-banner-big">
      <router-link to="/other"
        ><img
          src="../assets/dummy-banner-big.png"
          alt="banner-big"
          class="banner-big"
      /></router-link>
    </div>
    <div class="recommended">
      <h3>Recommend</h3>
      <ul>
        <li v-for="recommend in recommendList" :key="recommend.id">
          <router-link to="/other">
            <img src="../assets/room-thumbnail.png" alt="room-1" />
            <div class="texts">
              <p>{{ recommend.title }}</p>
              <p>{{ recommend.date }}</p>
            </div></router-link
          >
        </li>
      </ul>
    </div>
    <ul class="banner-list">
      <li>
        <router-link to="/other"
          ><img src="../assets/dummy-banner-small.png" alt="small-banner"
        /></router-link>
      </li>
      <li>
        <router-link to="/other"
          ><img src="../assets/dummy-banner-small.png" alt="small-banner"
        /></router-link>
      </li>
      <li>
        <router-link to="/other"
          ><img src="../assets/dummy-banner-small.png" alt="small-banner"
        /></router-link>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "HomeSidebar",
  data() {
    return {
      recommendList: [
        {
          id: "01",
          title:
            "サンプルテキストサンプルテキストサンプルテキストサンプルテキスト",
          date: "2016.03.26",
          image: "",
        },
        {
          id: "02",
          title:
            "サンプルテキストサンプルテキストサンプルテキストサンプルテキスト",
          date: "2016.03.26",
          image: "",
        },
        {
          id: "03",
          title:
            "サンプルテキストサンプルテキストサンプルテキストサンプルテキスト",
          date: "2016.03.26",
          image: "",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.side-bar {
  float: right;
  width: 30%;
  background-color: #efefef;
  padding: 20px;
  padding-bottom: 18px;

  .banner-big {
    display: block;
    margin: auto;
  }

  ul {
    list-style-type: none;
    padding: 0;
    margin: 0;
    margin-bottom: 36px;
  }

  a {
    text-decoration: none;
    color: #000;

    &::after {
      content: "";
      clear: both;
      display: table;
    }
    &:visited {
      text-decoration: none;
      color: #000;
    }
  }

  img {
    width: 100%;
  }

  .recommended {
    h3 {
      font-weight: 500;
      font-size: 24px;
      display: block;
      border-bottom: 2px solid black;
      text-align: center;
    }
    li {
      margin-bottom: 16px;
    }

    img {
      float: left;
      width: 20%;
    }
    img + div {
      float: right;
      width: 78%;
    }

    p {
      margin: 0;

      &:first-child {
        font-weight: bold;
        font-size: 13px;
      }
      &:last-child {
        font-size: 12px;
        color: #999;
      }
    }
  }

  .banner-list {
    margin: 0;
    li:not(:last-child) {
      margin-bottom: 18px;
    }
  }
}
</style>
