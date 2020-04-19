<template>
  <div class="contents">
    <ul>
      <li v-for="article in articles" :key="article.id">
        <router-link to="/other" class=" article"
          ><img
            src="../assets/room-thumbnail.png"
            alt="room-1"
            class="room-1"
          />
          <img
            src="../assets/room-thumbnail-2.png"
            alt="house-2"
            class="house-2"
          />
          <div>
            <p class="date">{{ article.date }}</p>
            <p class="title">{{ article.title }}</p>
            <p class="desc">{{ article.description }}</p>
          </div></router-link
        >
      </li>
    </ul>
    <router-link to="/other" tag="button" class="more-btn"
      >More <span><font-awesome-icon icon="angle-right"/></span
    ></router-link>
  </div>
</template>

<script>
export default {
  name: "HomeContents",
  data() {
    return {
      articles: [
        {
          id: "11",
          title:
            "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト",
          description:
            "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト…",
          date: "2016.01.01",
          image: ""
        },
        {
          id: "12",
          title:
            "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト",
          description:
            "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト…",
          date: "2016.01.01",
          image: ""
        },
        {
          id: "13",
          title:
            "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト",
          description:
            "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト…",
          date: "2016.01.01",
          image: ""
        },
        {
          id: "14",
          title:
            "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト",
          description:
            "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト…",
          date: "2016.01.01",
          image: ""
        },
        {
          id: "15",
          title:
            "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト",
          description:
            "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト…",
          date: "2016.01.01",
          image: ""
        },
        {
          id: "16",
          title:
            "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト",
          description:
            "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト…",
          date: "2016.01.01",
          image: ""
        },
        {
          id: "17",
          title:
            "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト",
          description:
            "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト…",
          date: "2016.01.01",
          image: ""
        },
        {
          id: "18",
          title:
            "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト",
          description:
            "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト…",
          date: "2016.01.01",
          image: ""
        },
        {
          id: "19",
          title:
            "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト",
          description:
            "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト…",
          date: "2016.01.01",
          image: ""
        },
        {
          id: "20",
          title:
            "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト",
          description:
            "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト…",
          date: "2016.01.01",
          image: ""
        }
      ]
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.article {
  text-decoration: none;
  color: #000;
  p {
    margin: 0;
  }
  img {
    float: left;
    width: 28%;

    &.house-2 {
      display: none;
    }
  }
  div {
    float: right;
    width: 68%;
    padding-left: 14px;

    .date {
      color: #999;
      font-size: 13px;
      margin-bottom: 12px;
    }
    .title {
      font-weight: bold;
      font-size: 18px;
      margin-bottom: 10px;
    }
    .desc {
      font-weight: 500;
      font-size: 13px;
    }
  }
  &:hover {
    .title {
      color: #e7ba2f;
    }
    .room-1 {
      display: none;
    }
    .house-2 {
      display: block;
    }
  }
  &:visited {
    text-decoration: none;
    color: #000;
  }
  &::after {
    content: "";
    clear: both;
    display: table;
  }
}

.contents {
  float: left;
  width: 64%;
}
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin-bottom: 10px;
}

.more-btn {
  width: 50%;
  padding: 10px 20px;
  border: 1px solid #ddd;
  color: #fff;
  background-color: #333;
  font-size: 20px;
  font-weight: 500;
  cursor: pointer;
  display: block;
  margin: auto;
  margin-top: 28px;

  span {
    float: right;
  }
}
</style>
