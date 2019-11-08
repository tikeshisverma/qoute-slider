<template>
  <div class="slider-wrapper">
    <div class="slider-content">
      <button @click="previous" class="previous">
        <svg height="52pt" viewBox="0 0 512 512" width="52pt" xmlns="http://www.w3.org/2000/svg">
          <path
            d="m224 382c-5.140625 0-10.277344-1.96875-14.1875-5.902344-7.785156-7.835937-7.746094-20.5.089844-28.285156l78.203125-77.695312c3.800781-3.777344 5.894531-8.792969 5.894531-14.117188s-2.09375-10.335938-5.894531-14.113281l-78.203125-77.699219c-7.835938-7.785156-7.875-20.445312-.089844-28.28125s20.449219-7.878906 28.285156-.09375l78.199219 77.699219c11.417969 11.339843 17.703125 26.429687 17.703125 42.488281s-6.285156 31.148438-17.703125 42.488281l-78.199219 77.699219c-3.902344 3.875-9 5.8125-14.097656 5.8125zm164.460938 93.105469c9.449218-5.722657 12.46875-18.019531 6.746093-27.46875-5.726562-9.449219-18.023437-12.46875-27.46875-6.742188-33.59375 20.347657-72.230469 31.105469-111.738281 31.105469-119.101562 0-216-96.898438-216-216s96.898438-216 216-216 216 96.898438 216 216c0 42.589844-12.664062 84.042969-36.625 119.882812-6.140625 9.183594-3.671875 21.605469 5.511719 27.742188 9.179687 6.140625 21.601562 3.671875 27.742187-5.507812 28.371094-42.441407 43.371094-91.585938 43.371094-142.117188 0-68.378906-26.628906-132.667969-74.980469-181.019531-48.351562-48.351563-112.640625-74.980469-181.019531-74.980469s-132.667969 26.628906-181.019531 74.980469c-48.351563 48.351562-74.980469 112.640625-74.980469 181.019531s26.628906 132.667969 74.980469 181.019531c48.351562 48.351563 112.640625 74.980469 181.019531 74.980469 46.8125 0 92.617188-12.757812 132.460938-36.894531zm0 0"
          />
          <linearGradient id="chevron">
            <stop offset="5%" stop-color="#00d301" />
            <stop offset="55%" stop-color="#36c275" />
            <stop offset="95%" stop-color="#00a562" />
          </linearGradient>
        </svg>
      </button>
      <transition name="slide-fade" tag="div" mode="out-in">
        <h2 class="slider-qoute" v-for="i in [currentQoute]" :key="i.qouter">
          {{currentQoute.qoute}}
          <br />
          <span class="text-highlight slider-qouter">- {{currentQoute.qouter}}</span>
        </h2>
      </transition>
      <button @click="next" class="next">
        <svg height="52pt" viewBox="0 0 512 512" width="52pt" xmlns="http://www.w3.org/2000/svg">
          <path
            d="m224 382c-5.140625 0-10.277344-1.96875-14.1875-5.902344-7.785156-7.835937-7.746094-20.5.089844-28.285156l78.203125-77.695312c3.800781-3.777344 5.894531-8.792969 5.894531-14.117188s-2.09375-10.335938-5.894531-14.113281l-78.203125-77.699219c-7.835938-7.785156-7.875-20.445312-.089844-28.28125s20.449219-7.878906 28.285156-.09375l78.199219 77.699219c11.417969 11.339843 17.703125 26.429687 17.703125 42.488281s-6.285156 31.148438-17.703125 42.488281l-78.199219 77.699219c-3.902344 3.875-9 5.8125-14.097656 5.8125zm164.460938 93.105469c9.449218-5.722657 12.46875-18.019531 6.746093-27.46875-5.726562-9.449219-18.023437-12.46875-27.46875-6.742188-33.59375 20.347657-72.230469 31.105469-111.738281 31.105469-119.101562 0-216-96.898438-216-216s96.898438-216 216-216 216 96.898438 216 216c0 42.589844-12.664062 84.042969-36.625 119.882812-6.140625 9.183594-3.671875 21.605469 5.511719 27.742188 9.179687 6.140625 21.601562 3.671875 27.742187-5.507812 28.371094-42.441407 43.371094-91.585938 43.371094-142.117188 0-68.378906-26.628906-132.667969-74.980469-181.019531-48.351562-48.351563-112.640625-74.980469-181.019531-74.980469s-132.667969 26.628906-181.019531 74.980469c-48.351563 48.351562-74.980469 112.640625-74.980469 181.019531s26.628906 132.667969 74.980469 181.019531c48.351562 48.351563 112.640625 74.980469 181.019531 74.980469 46.8125 0 92.617188-12.757812 132.460938-36.894531zm0 0"
          />
          <linearGradient id="chevron">
            <stop offset="5%" stop-color="#00d301" />
            <stop offset="55%" stop-color="#36c275" />
            <stop offset="95%" stop-color="#00a562" />
          </linearGradient>
        </svg>
      </button>
    </div>
    <button @click="download" class="download">
      <svg height="15pt" viewBox="0 0 512 512" width="15pt" xmlns="http://www.w3.org/2000/svg">
        <path
          d="m224 382c-5.140625 0-10.277344-1.96875-14.1875-5.902344-7.785156-7.835937-7.746094-20.5.089844-28.285156l78.203125-77.695312c3.800781-3.777344 5.894531-8.792969 5.894531-14.117188s-2.09375-10.335938-5.894531-14.113281l-78.203125-77.699219c-7.835938-7.785156-7.875-20.445312-.089844-28.28125s20.449219-7.878906 28.285156-.09375l78.199219 77.699219c11.417969 11.339843 17.703125 26.429687 17.703125 42.488281s-6.285156 31.148438-17.703125 42.488281l-78.199219 77.699219c-3.902344 3.875-9 5.8125-14.097656 5.8125zm164.460938 93.105469c9.449218-5.722657 12.46875-18.019531 6.746093-27.46875-5.726562-9.449219-18.023437-12.46875-27.46875-6.742188-33.59375 20.347657-72.230469 31.105469-111.738281 31.105469-119.101562 0-216-96.898438-216-216s96.898438-216 216-216 216 96.898438 216 216c0 42.589844-12.664062 84.042969-36.625 119.882812-6.140625 9.183594-3.671875 21.605469 5.511719 27.742188 9.179687 6.140625 21.601562 3.671875 27.742187-5.507812 28.371094-42.441407 43.371094-91.585938 43.371094-142.117188 0-68.378906-26.628906-132.667969-74.980469-181.019531-48.351562-48.351563-112.640625-74.980469-181.019531-74.980469s-132.667969 26.628906-181.019531 74.980469c-48.351563 48.351562-74.980469 112.640625-74.980469 181.019531s26.628906 132.667969 74.980469 181.019531c48.351562 48.351563 112.640625 74.980469 181.019531 74.980469 46.8125 0 92.617188-12.757812 132.460938-36.894531zm0 0"
        />
      </svg>
      download
    </button>
    <canvas ref="canvas" width="800" height="200" style="border:1px solid #BBB;"></canvas>
  </div>
</template>
<script>
export default {
  name: "Slider",

  computed: {
    currentQoute() {
      const qouteString = this.quotes[
        Math.abs(this.counter) % this.quotes.length
      ];
      const [qoute, qouter] = qouteString.split("-");
      return {
        qoute,
        qouter
      };
    }
  },
  data() {
    return {
      counter: 0
    };
  },
  watch: {
    currentQoute: function() {
      this.renderQoute();
    }
  },
  props: ["quotes"],
  mounted() {
    this.renderQoute();
  },
  methods: {
    renderQoute() {
      // Get canvas context
      const canvasElement = this.$refs.canvas;
      var ctx = canvasElement.getContext("2d");
      // Clear the canvas
      ctx.clearRect(0, 0, canvasElement.width, canvasElement.height);
      // Insert stuff into canvas
      ctx.fillStyle = "black";
      ctx.font = "20px Chonburi";
      ctx.fillStyle = "red";
      ctx.textAlign = "center";
      ctx.textBaseline = "middle";
      // ctx.fillText(binding.value, 10, 50);
      const maxWidth = 400;
      const lineHeight = 30;
      let x = canvasElement.width / 2;
      let y = canvasElement.height / 2;
      this.wrapText(
        ctx,
        `${this.currentQoute.qoute} - ${this.currentQoute.qouter}`,
        x,
        y,
        maxWidth,
        lineHeight
      );
    },
    download() {
      this.exportCanvasAsPNG(this.$refs.canvas, "qoute");
    },
    next() {
      this.counter = this.counter + 1;
    },
    previous() {
      this.counter = this.counter - 1;
    },
    exportCanvasAsPNG(canvasElement, fileName) {
      var MIME_TYPE = "image/png";

      var imgURL = canvasElement.toDataURL(MIME_TYPE);

      var dlLink = document.createElement("a");
      dlLink.download = fileName;
      dlLink.href = imgURL;
      dlLink.dataset.downloadurl = [
        MIME_TYPE,
        dlLink.download,
        dlLink.href
      ].join(":");

      document.body.appendChild(dlLink);
      dlLink.click();
      document.body.removeChild(dlLink);
    },
    wrapText(ctx, text, x, y, maxWidth, lineHeight) {
      var words = text.split(" ");
      var line = "";

      for (var n = 0; n < words.length; n++) {
        var testLine = line + words[n] + " ";
        var metrics = ctx.measureText(testLine);
        var testWidth = metrics.width;
        if (testWidth > maxWidth && n > 0) {
          ctx.fillText(line, x, y);
          line = words[n] + " ";
          y += lineHeight;
        } else {
          line = testLine;
        }
      }
      ctx.fillText(line, x, y);
    }
  },
  created() {}
};
</script>
<style>
.slider-wrapper {
  display: flex;
  align-items: center;
  flex-direction: column;
  justify-content: center;
  height: 100%;
}

canvas {
  display: none;
}

.slider-content {
  display: flex;
  width: 80%;
  justify-content: space-between;
  text-size-adjust: auto;
  position: relative;
}
.slider-content svg:hover {
  fill: url(#chevron);
}

.slider-qoute {
  font-size: 8vh;
  font-weight: initial;
  margin: 0em 1em;
  display: flex;
  flex-direction: column;
}

.previous svg,
.next svg {
  width: 6vw;
}

.slider-qouter {
  align-self: flex-end;
}
button {
  background: transparent;
  border: none;
  outline: none;
  cursor: pointer;
}
.previous {
  transform: scaleX(-1);
}

.download {
  display: flex;
  align-items: center;
  position: fixed;
  bottom: 1em;
  right: 1em;
  cursor: pointer;
  text-transform: uppercase;
  border-radius: 2px;
  font-size: 1em;
  font-weight: 400;
  font-style: normal;
  font-stretch: normal;
  line-height: normal;
  letter-spacing: normal;
  text-decoration: none;
  margin: 0;
  -webkit-transition: all 0.1s linear;
  transition: all 0.1s linear;
  border-radius: 1em;
  color: #fff;
  background-color: #35cd61;
  min-width: 9em;
  min-height: 2em;
  -webkit-text-fill-color: #fff;
  text-fill-color: #fff;
  z-index: 1;
}
.download svg {
  transform: rotate(90deg);
  margin-right: 1em;
  fill: white;
}
.text-highlight {
  background-image: linear-gradient(
    -100deg,
    rgba(255, 250, 150, 0.15),
    rgba(255, 250, 150, 0.8) 100%,
    rgba(255, 250, 150, 0.25)
  );
  display: inline;
  border-radius: 0.25em;
  font-family: "Poiret One";
  color: #000;
  background: url("http://tikesh.me/images/highlight-brush-stroke.4a9d80854f8a3261232c5f120059a6ed.svg");
  background-repeat: no-repeat;
  background-size: 100% 200%;
  padding: 20px;
  background-position: 48%;
}
.slide-fade-enter-active {
  transition: all 0.3s ease;
}
.slide-fade-leave-active {
  transition: all 0.8s cubic-bezier(1, 0.5, 0.8, 1);
}
.slide-fade-enter, .slide-fade-leave-to
/* .slide-fade-leave-active below version 2.1.8 */ {
  transform: translateY(50px);
  opacity: 0;
}
@media only screen and (max-width: 1000px) {
  .slider-qoute {
    font-size: 5vh;
  }
}
@media only screen and (max-width: 600px) {
  .slider-content {
    flex-wrap: wrap;
    width: 90%;
  }
  .previous {
    order: 2;
  }
  .slider-qoute {
    order: 1;
  }
  .next {
    order: 3;
  }
}
@media only screen and (max-width: 420px) {
  .slider-qoute {
    font-size: 4vh;
  }
}
</style>;
