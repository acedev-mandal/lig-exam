<template>
  <div class="slideshow">
    <!-- Slideshow container -->
    <div class="slideshow-container">
      <!-- Full-width images with number and caption text -->
      <div
        class="mySlides"
        :class="{ 'slide-left': leftSlide, 'slide-right': rightSlide }"
      >
        <div class="numbertext">キャッチコピーが入ります。</div>
        <img :src="images[0]" style="width:100%" />
        <div class="text">
          サンプルテキストサンプルテキストサンプルテキストサンプルテキスト
          サンプルテキストサンプルテキストサンプルテキストサンプルテキスト
        </div>
      </div>

      <div
        class="mySlides"
        :class="{ 'slide-left': leftSlide, 'slide-right': rightSlide }"
      >
        <div class="numbertext">キャッチコピーが入ります。</div>
        <img :src="images[1]" style="width:100%" />
        <div class="text">
          サンプルテキストサンプルテキストサンプルテキストサンプルテキスト
          サンプルテキストサンプルテキストサンプルテキストサンプルテキスト
        </div>
      </div>

      <div
        class="mySlides"
        :class="{ 'slide-left': leftSlide, 'slide-right': rightSlide }"
      >
        <div class="numbertext">キャッチコピーが入ります。</div>
        <img :src="images[2]" style="width:100%" />
        <div class="text">
          サンプルテキストサンプルテキストサンプルテキストサンプルテキスト
          サンプルテキストサンプルテキストサンプルテキストサンプルテキスト
        </div>
      </div>

      <!-- Next and previous buttons -->
      <a class="prev" @click="plusSlides(-1)" v-show="slideIndex > 1"
        ><font-awesome-icon icon="angle-left"
      /></a>
      <a class="next" @click="plusSlides(1)" v-show="slideIndex < 3"
        ><font-awesome-icon icon="angle-right"
      /></a>
    </div>
    <!-- The dots/circles -->
    <div class="pager">
      <span class="dot" @click="currentSlide(1)"></span>
      <span class="dot" @click="currentSlide(2)"></span>
      <span class="dot" @click="currentSlide(3)"></span>
    </div>
  </div>
</template>

<script>
export default {
  name: "HeaderSlider",
  data() {
    return {
      slideIndex: 1,
      leftSlide: false,
      rightSlide: false,
      slideLogger: 0,
      images: [
        "https://images.unsplash.com/photo-1506260408121-e353d10b87c7?ixlib=rb-1.2.1&q=85&fm=jpg&crop=entropy&cs=srgb&w=1600&fit=max&ixid=eyJhcHBfaWQiOjE0NTg5fQ",
        "https://images.unsplash.com/photo-1523712999610-f77fbcfc3843?ixlib=rb-1.2.1&q=85&fm=jpg&crop=entropy&cs=srgb&w=1600&fit=max&ixid=eyJhcHBfaWQiOjE0NTg5fQ",
        "https://images.unsplash.com/photo-1524260855046-f743b3cdad07?ixlib=rb-1.2.1&q=85&fm=jpg&crop=entropy&cs=srgb&w=1600&fit=max&ixid=eyJhcHBfaWQiOjE0NTg5fQ",
      ],
    };
  },
  mounted() {
    this.showSlides(this.slideIndex);
  },
  methods: {
    showSlides(n) {
      let i;
      const slides = document.getElementsByClassName("mySlides");
      const dots = document.getElementsByClassName("dot");
      if (n > slides.length) {
        this.slideIndex = 1;
      }
      if (n < 1) {
        this.slideIndex = slides.length;
      }
      for (i = 0; i < slides.length; i++) {
        slides[i].style.display = "none";
      }
      for (i = 0; i < dots.length; i++) {
        dots[i].className = dots[i].className.replace(" active", "");
      }
      slides[this.slideIndex - 1].style.display = "block";
      dots[this.slideIndex - 1].className += " active";
    },
    // Next/previous controls
    plusSlides(n) {
      this.leftSlide = n > 0;
      this.rightSlide = n < 0;
      this.showSlides((this.slideIndex += n));
    },

    // Thumbnail image controls
    currentSlide(n) {
      this.leftSlide = n > this.slideLogger;
      this.rightSlide = n < this.slideLogger;
      this.slideLogger = n;
      this.showSlides((this.slideIndex = n));
    },
  },
};
</script>

<style lang="scss" scoped>
* {
  box-sizing: border-box;
}

.slideshow {
  position: relative;
}

/* Slideshow container */
.slideshow-container {
  width: 100%;
  position: relative;
  margin: auto;
  overflow: hidden;
}

/* Hide the images by default */
.mySlides {
  display: none;
}

/* Next & previous buttons */
.prev,
.next {
  cursor: pointer;
  position: absolute;
  top: 40%;
  width: auto;
  margin-top: -22px;
  padding: 16px;
  color: white;
  font-weight: bold;
  font-size: 124px;
  border-radius: 0 3px 3px 0;
  user-select: none;
}

/* Position the "next button" to the right */
.next {
  right: 0;
  border-radius: 3px 0 0 3px;
}
.prev {
  margin-left: 98px;
}
.next {
  margin-right: 98px;
}

/* Caption text */
.text {
  color: #f2f2f2;
  font-size: 16px;
  font-weight: 500;
  padding: 8px 12px;
  position: absolute;
  bottom: 356px;
  width: 40%;
  text-align: center;
  left: 50%;
  margin-left: -266px;
}

/* Number text (1/3 etc) */
.numbertext {
  color: #f2f2f2;
  padding: 8px 12px;
  position: absolute;
  font-weight: bold;
  font-size: 60px;
  left: 50%;
  margin-left: -406px;
  top: 40%;
  margin-top: -50px;
}

/* The dots/bullets/indicators */
.dot {
  cursor: pointer;
  height: 15px;
  width: 15px;
  margin: 0 2px;
  background-color: #fff;
  border-radius: 50%;
  display: inline-block;
  transition: background-color 0.6s ease;
}

.active,
.dot:hover {
  background-color: #e7ba2f;
}

.pager {
  text-align: center;
  position: relative;
  top: -40px;
}

/* Sliding animation */
.slide-left {
  -webkit-animation-name: slide-left;
  -webkit-animation-duration: 1.5s;
  animation-name: slide-left;
  animation-duration: 0.8s;
}

@-webkit-keyframes slide-left {
  from {
    transform: translateX(100%);
    opacity: 0.4;
  }
  to {
    transform: translateX(0px);
    opacity: 1;
  }
}

@keyframes slide-left {
  from {
    transform: translateX(100%);
    opacity: 0.4;
  }
  to {
    transform: translateX(0px);
    opacity: 1;
  }
}

.slide-right {
  -webkit-animation-name: slide-right;
  -webkit-animation-duration: 1.5s;
  animation-name: slide-right;
  animation-duration: 0.8s;
}

@-webkit-keyframes slide-right {
  from {
    transform: translateX(-100%);
    opacity: 0.4;
  }
  to {
    transform: translateX(0px);
    opacity: 1;
  }
}

@keyframes slide-right {
  from {
    transform: translateX(-100%);
    opacity: 0.4;
  }
  to {
    transform: translateX(0px);
    opacity: 1;
  }
}
</style>
