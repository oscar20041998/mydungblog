<template>
  <div
    id="carouselExampleControls"
    class="carousel slide carousel-fade"
    data-bs-ride="carousel"
  >
    <div class="carousel-inner">
      <div class="carousel-item active">
        <img
          src="https://files.fm/thumb_show.php?i=tvzshtujb"
          class="d-block w-100 img-fluid"
          alt="..."
        />
      </div>
      <div v-for="img in listImage" v-bind:key="img.id" class="carousel-item">
        <img :src="img.src" class="d-block w-100 img-fluid" />
      </div>
    </div>
    <button
      class="carousel-control-prev"
      type="button"
      data-bs-target="#carouselExampleControls"
      data-bs-slide="prev"
    >
      <span class="carousel-control-prev-icon" aria-hidden="true"></span>
      <span class="visually-hidden">Previous</span>
    </button>
    <button
      class="carousel-control-next"
      type="button"
      data-bs-target="#carouselExampleControls"
      data-bs-slide="next"
    >
      <span class="carousel-control-next-icon" aria-hidden="true"></span>
      <span class="visually-hidden">Next</span>
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      slide: 0,
      sliding: null,
      listImage: [
        {
          id: btoa("image-03"),
          src: "https://files.fm/thumb_show.php?i=7d5qy69et",
        },
        {
          id: btoa("image-05"),
          src: "https://files.fm/thumb_show.php?i=9n444bjfy",
        },
      ],
    };
  },
  methods: {},
};
</script>

<style scoped>
.carousel-item:hover {
  opacity: 0.2;
}

@media (max-height: 800px) {
  img {
    height: 350px !important;
  }
}

@media (max-height: 1300px) {
  img {
    height: 480px;
  }
}
</style>
