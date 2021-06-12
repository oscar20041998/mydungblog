<template>
  <div class="mt-4">
    <h4>Popular post</h4>
    <b-row>
      <template v-for="post in listPost">
        <b-col sm="3" v-bind:key="post.id">
          <b-card
            v-bind:key="post.id"
            :img-src="post.image"
            img-alt="Card image"
            :title="post.title"
            :sub-title="post.createdDate"
            img-top
            style="max-width: 30rem"
          >
            <b-card-text>
              {{ post.description }}
            </b-card-text>
            <div style="text-align: right">
              <b-button
                v-b-modal.modal-lg
                variant="primary"
                size="sm"
                @click="clickShowPopupReadMore(post.id)"
                >More...</b-button
              >
            </div>
          </b-card>
        </b-col>
      </template>
    </b-row>
    <PopupReadMore :tilte="detailPost.tilte"></PopupReadMore>
  </div>
</template>
<script>
import PopupReadMore from "../components/PopupReadMore.vue";
export default {
  name: "PostPopular",
  components: {
    PopupReadMore,
  },
  data() {
    return {
      detailPost: {
        id: "",
        title: "",
        content: "",
        image: "",
        createdDate: "",
      },
      listPost: [
        {
          id: "001",
          title: "LOOK BACK",
          image: "https://files.fm/thumb_show.php?i=cspbv4bjc",
          description:
            "Hi there! 🙆Just my 1 month at work !! I have not graduated yet, god, ...",
          content: "",
          createdDate: "14/11/2020",
        },
        {
          id: "002",
          title: "A LITTLE CONFESION AT NIGHT !",
          image: "https://files.fm/thumb_show.php?i=5tgff2xzy",
          description: "Now that I am 22, I must have my plans. Of course,...",
          content: "",
          createdDate: "03/04/2020",
        },
      ],
    };
  },

  methods: {
    clickShowPopupReadMore(idPost) {
      this.listPost.map(function (value, key) {
        if (idPost === value.id) {
          this.detailPost.id = key;
          this.detailPost.title = value.title;
          this.detailPost.image = value.image;
          this.detailPost.content = value.content;
          this.detailPost.createdDate = value.createdDate;
        }
      });
    },
  },
};
</script>
<style scoped>
.card-img,
.card-img-top,
.card-img-bottom {
  width: 100%;
  height: 220px;
}
.card-title {
  font-family: Impact, Haettenschweiler, "Arial Narrow Bold", sans-serif;
  text-align: left;
  color: #a28089;
}

.card-subtitle,
.card-text {
  text-align: left;
}

.card-body {
  background-color: #edf7f6;
}

.btn.btn-primary {
  right: 10px !important;
  bottom: 5px !important;
  border-radius: 0px !important;
}

.card {
  margin-top: 10px;
}
</style>
