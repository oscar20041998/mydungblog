<template>
  <div class="mt-4">
    <h4>Popular post</h4>
    <template v-for="post in listPost">
      <b-card
        v-bind:key="post.id"
        :img-src="post.image"
        img-alt="Card image"
        :title="post.title"
        :sub-title="post.createdDate"
        img-left
        class="mb-3"
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
        <PopupReadMore :tilte="detailPost.tilte"></PopupReadMore>
      </b-card>
    </template>
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
            "Hi there! 🙆Just my 1 month at work !! I have not graduated yet, god, waiting for a diploma and graduation ceremony is too long. At the end of November 2020, it's my Graduation Ceremony, so cool, yeyeyehh 🙌🙌Look back to see what's cool ... haha ​​:)). Here I will summarize the past 1 month, short, not too long!",
          content: "",
          createdDate: "14/11/2020",
        },
        {
          id: "002",
          title: "A LITTLE CONFESION AT NIGHT !",
          image: "https://files.fm/thumb_show.php?i=5tgff2xzy",
          description:
            "Now that I am 22, I must have my plans. Of course, I always want to be the most perfect version and I'm working on it.😆 Do you know? This is the first time I do this- writing about myself on the blog. No problem, as long as I can feel comfortable. ^^ ok right! ☝☝",
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
.card-img-left {
  height: 220px !important;
  width: 330px !important;
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
</style>
