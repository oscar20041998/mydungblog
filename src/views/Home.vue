<template>
  <div>
    <b-carousel
      id="carousel-1"
      v-model="slide"
      :interval="8000"
      controls
      indicators
      background="#ababab"
      img-width="1024"
      img-height="auto"
      style="text-shadow: 1px 1px 2px #333"
      label-next=""
      label-prev=""
    >
      <template v-for="img in listImage">
        <b-carousel-slide v-bind:key="img.id" :img-src="img.src"></b-carousel-slide>
      </template>
    </b-carousel>
    <hr class="my-4" />
    <PostPoppularComponent></PostPoppularComponent>
  </div>
</template>

<script>
import PostPoppularComponent from "../components/PopularPost.vue";
export default {
  name: "Home",
  components: {
    PostPoppularComponent,
  },
  data() {
    return {
      slide: 0,
      sliding: null,
      listImage: [
        {
          id: btoa("image-01"),
          src: "https://files.fm/thumb_show.php?i=7d5qy69et",
        },
        {
          id: btoa("image-02"),
          src: "https://files.fm/thumb_show.php?i=6qf9aauer",
        },
        {
          id: "image-03",
          src: "https://files.fm/thumb_show.php?i=8r6kw2uz4",
        },
        {
          id: btoa("image-04"),
          src: "https://files.fm/thumb_show.php?i=tvzshtujb",
        },
      ],
    };
  },
  methods: {},
};
</script>

<style scoped>
.carousel-item:hover {
  opacity: 0.6;
  transition: all 0.5s;
}
</style>
