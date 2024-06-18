<!-- <template>
  <v-main class="">
    <v-container fluid class="pa-0 ma-0">
      <v-row class="Badge">
        <v-col md="7" cols="12" class="content--box pa-0 ma-0">
          <h2 class="text-h4">Badges</h2>
          <p>
            Now that you are here, how about personalising your DevFest India
            2023
            <br />
            profile? Upload an image and generate a personalised badge with the
            DevFest <br />India 2023 frame. Also share your image using
            #DevFestIndia on different <br />social platforms.
          </p>
          <h3 class="mt-5">Select Image</h3>
          <v-btn class="mt-4 mb-5 action_btn" rounded
            >Upload Image
            <v-icon>mdi-tray-arrow-up</v-icon>
          </v-btn>
          <template>
            <v-btn-toggle v-model="selected" mandatory>
              <v-btn value="1">Segment 1</v-btn>
              <v-btn value="2">Segment 2</v-btn>
              <v-btn value="3">Segment 3</v-btn>
            </v-btn-toggle>
          </template>

          <div class="segmented-control">
            <h4></h4>
            <input type="radio" name="segmented" id="segment-1" checked />
            <label for="segment-1">Original</label>
            <input type="radio" name="segmented" id="segment-2" />
            <label for="segment-2">Square</label>
            <input type="radio" name="segmented" id="segment-3" />
            <label for="segment-3">Circle</label>
          </div>

          <p>
            *  We respect your privacy and are not storing your pictures on our
            servers.
          </p>
        </v-col>
        <v-col md="5" cols="12">
          <div class="grey-box">
            <v-img
              src="/assets/img/core/badge.svg"
              lazy-src="/assets/img/core/badge.svg"
              max-height="350"
              max-width="100%"
            ></v-img>
          </div>
        </v-col>
      </v-row>
    </v-container>
  </v-main>
</template>

<script>
export default {
  data() {
    return {
      selected: 1,
    };
  },
};
</script>

<style scoped>
.grey-box {
  background-color: #eeeeee;
  border-radius: 1rem;
  max-height: 100%;
  max-width: 60%;
  padding: 3rem 2rem;
}
.img_shape .v-img {
  display: flex;
  align-items: flex-start;
  justify-content: center;
}
.content--box {
  display: flex;
  align-items: flex-start;
  flex-direction: column;
  justify-content: center;
}
.action_btn {
  background: linear-gradient(90deg, #ffcb32, #34a853 80%);
  color: #000;
  box-shadow: none;
  border: 2px solid black;
}
.segmented-control {
  display: flex;
  border: 1px solid #ccc;
  border-radius: 5px;
  overflow: hidden;
}

.segmented-control input[type="radio"] {
  display: none;
}

.segmented-control label {
  flex: 1;
  padding: 10px;
  text-align: center;
  cursor: pointer;
  background-color: #f9f9f9;
  transition: background-color 0.3s;
}

.segmented-control input[type="radio"]:checked + label {
  background-color: #007bff;
  color: white;
}

.segmented-control label:hover {
  background-color: #e9e9e9;
}
</style> -->

<template>
  <v-main class="my-md-10 my-0 px-3">
    <v-container fluid>
      <!-- Mobile -->
      <v-row>
        <v-col md="12" lg="12" class="d-block d-sm-block d-md-none px-0">
          <p class="google-font gdg-heading text-h4 mb-4">Badges</p>
          <p class="my-0 mb-8 h1-subheading google-font">
            Now that you are here, how about personalising your DevFest India
            2024 profile? Upload an image and generate a personalised badge with
            the DevFest India 2024 frame. Also share your image using
            #DevFestIndia on different social platforms.
          </p>
        </v-col>
      </v-row>
      <!-- Mobile -->

      <!-- Desktop -->
      <v-row class="mb-md-10">
        <v-col
          md="6"
          class="order-md-1 order-sm-2 order-2 px-md-7 mt-3 px-0 mb-md-13"
        >
          <div class="d-none d-sm-none d-md-block mb-10">
            <p class="google-font gdg-heading text-h3 mb-4">Badges</p>

            <p class="google-font" style="font-size: 18px">
              Now that you are here, how about personalising your DevFest India
              2024 profile? Upload an image and generate a personalised badge
              with the DevFest India 2024 frame. Also share your image using
              #DevFestIndia on different social platforms.
            </p>
          </div>
          <div class="input">
            <label class="google-font mb-3" style="font-size: 110%"
              >Select a Image</label
            >
            <br />

            <v-btn
              class="action_btn mt-4 mb-5"
              large
              @click="uploadImage()"
              rounded
              style="text-transform: capitalize"
            >
              Upload Image
              <v-icon>mdi-tray-arrow-up</v-icon>
            </v-btn>
            <input
              class="profile-input"
              type="file"
              accept="image/*"
              @change="upload"
              hidden
            />
          </div>
          <div class="mt-5">
            <label class="google-font mb-5" style="font-size: 110%"
              >Image Shape</label
            >
            <br />
            <v-btn-toggle
              class="mt-3"
              rounded
              v-model="shapeData"
              color="#eeeeee"
            >
              <v-btn
                value="original"
                class="mx-0 px-5 pb-0"
                @click="changeShape('original')"
                >Orignal</v-btn
              >
              <v-btn
                class="mx-0 pb-0 px-5"
                value="Square"
                @click="changeShape('Square')"
                >Square</v-btn
              >
              <v-btn
                class="mx-0 pb-0 px-5"
                value="circle"
                @click="changeShape('circle')"
                >Circle</v-btn
              >
            </v-btn-toggle>
          </div>
          <p class="mt-8 mb-15 mb-md-0">
            <span
              >*&nbsp; We respect your privacy and are not storing your pictures
              on our servers.</span
            >
          </p>
        </v-col>
        <v-col
          md="6"
          sm="12"
          cols="12"
          class="text-center py-md-10 py-5 order-md-2 order-sm-1 order-1"
          style="background: #eeeeee; border-radius: 18px"
        >
          <canvas class=""></canvas>
          <br /><br />
          <v-btn
            class="pb-0 mb-0 action_download_btn"
            rounded
            id="download"
            @click="download()"
            ><v-icon left>mdi-arrow-down-bold-circle-outline</v-icon
            >Download</v-btn
          >
        </v-col>
      </v-row>
      <!-- Desktop -->
    </v-container>
  </v-main>
</template>

<script>
import gdgImage from "@/assets/img/badge.png";

export default {
  name: "BadgeComponent",
  data: () => ({
    downloadbtn: false,
    canvas: null,
    shape: "original",
    image: "",
    shapeData: "original",
    ctx: null,
    banner: null,
  }),
  created() {
    document.title = "Badges | DevFest India 2024";
  },
  methods: {
    upload(e) {
      if (e && e.target.files && e.target.files[0]) {
        const reader = new FileReader();
        reader.onload = (event) => {
          const img = new Image();
          img.onload = () => {
            console.log("Image loaded successfully", img);
            this.image = img;
            this.draw();
          };
          img.onerror = (error) => {
            console.error("Error loading image", error);
          };
          img.src = event.target.result;
        };
        reader.onerror = (error) => {
          console.error("Error reading file", error);
        };
        reader.readAsDataURL(e.target.files[0]);
      }
    },
    uploadImage() {
      document.querySelector("input.profile-input").click();
      this.downloadbtn = true;
      document.getElementById("download").style.visibility = "visible";
    },
    changeShape(type) {
      this.shape = type;
      this.draw();
    },
    draw() {
      if (!this.canvas || !this.ctx) {
        console.error("Canvas or context is not initialized");
        return;
      }
      console.log("Drawing image with shape:", this.shape);

      this.canvas.width = 2500;
      this.canvas.height = 2500;

      this.ctx.clearRect(0, 0, this.canvas.width, this.canvas.height);
      if (this.image) {
        console.log("Drawing image:", this.image);

        switch (this.shape) {
          case "original": {
            this.canvas.width = this.image.width;
            this.canvas.height = this.image.height;
            this.ctx.drawImage(this.image, 0, 0);
            break;
          }
          default: {
            this.canvas.width = 2500;
            this.canvas.height = 2500;
            const hRatio = this.canvas.width / this.image.width;
            const vRatio = this.canvas.height / this.image.height;
            const ratio = Math.max(hRatio, vRatio);
            const x = (this.canvas.width - this.image.width * ratio) / 2;
            const y = (this.canvas.height - this.image.height * ratio) / 2;
            console.log(`Drawing image at (${x}, ${y}) with ratio ${ratio}`);

            this.ctx.drawImage(
              this.image,
              0,
              0,
              this.image.width,
              this.image.height,
              x,
              y,
              this.image.width * ratio,
              this.image.height * ratio
            );
            break;
          }
        }
      } else {
        console.log("No image to draw");

        this.ctx.fillStyle = "#fff";
        this.ctx.fillRect(0, 0, this.canvas.width, this.canvas.height);
      }
      const height =
        (this.banner.height / this.banner.width) * this.canvas.width;
      const y = this.canvas.height - height;
      const fontSize = this.canvas.width / 17.2;

      this.ctx.drawImage(
        this.banner,
        0,
        0,
        this.banner.width,
        this.banner.height,
        0,
        y,
        this.canvas.width,
        height
      );
      this.ctx.fillStyle = "#757575";
      this.ctx.textAlign = "center";
      this.ctx.textBaseline = "middle";
      this.ctx.font = `${fontSize}px Google Sans, sans-serif`;
      // ctx.fillText(category, canvas.width / 2, fontY)
      if (this.shape === "circle") {
        this.ctx.globalCompositeOperation = "destination-in";
        this.ctx.beginPath();
        this.ctx.arc(
          this.canvas.width / 2,
          this.canvas.height / 2,
          this.canvas.height / 2,
          0,
          Math.PI * 2
        );
        this.ctx.closePath();
        this.ctx.fill();
      }
    },
    download() {
      const a = document.createElement("a");
      const url = this.canvas.toDataURL("image/png;base64");
      a.download = "#DevFestIndia_badge.png";
      a.href = url;
      a.click();
    },
  },
  mounted() {
    this.canvas = document.querySelector("canvas");
    this.ctx = this.canvas.getContext("2d");
    this.image = "";
    this.shape = "original";
    this.downloadbtn = false;
    document.getElementById("download").style.visibility = "hidden";
    this.banner = new Image();
    this.banner.src = gdgImage;
    console.log(this.banner);
    this.banner.onload = () => {
      console.log("Banner loaded successfully");
      this.draw();
    };
    this.banner.onerror = (error) => {
      console.error("Error loading banner", error);
    };
  },
};
</script>
<style scoped>
.v-btn-group {
  border: 1px solid #757575;
  border-radius: 18px;
  background: transparent;
}
canvas {
  width: 1500px;
  max-width: 80%;
}
.action_btn {
  background: linear-gradient(90deg, #ffcb32, #34a853 80%);
  color: #000;
  box-shadow: none;
  border: 2px solid black;
}
.action_download_btn {
  background: linear-gradient(90deg, #faab31, #fcc731, #faab31 80%);
  color: #000;
  box-shadow: none;
  border: 1px solid black;
}

@media screen and (max-width: 860px) {
}
</style>
