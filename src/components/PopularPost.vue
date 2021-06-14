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
                :id="post.id"
                v-b-modal.modal-lg
                variant="primary"
                size="sm"
                squared
                @click="clickShowPopupReadMore(post.id)"
                ><b-icon icon="eye" scale="1" size="small"></b-icon> READ MORE
              </b-button>
              <b-tooltip :target="post.id" triggers="hover">
                Click to read <b>[ {{ post.title }} ]</b> content!
              </b-tooltip>
            </div>
          </b-card>
        </b-col>
      </template>
    </b-row>
    <PopupReadMore
      :title="this.detailPost.title"
      :headContent="this.detailPost.headContent"
      :bodyContent="this.detailPost.bodyContent"
      :endContent="this.detailPost.endContent"
      :image="this.detailPost.image"
      :createdDate="this.detailPost.createdDate"
    >
    </PopupReadMore>
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
        headContent: "",
        bodyContent: "",
        endContent: "",
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
          headContent:
            "Hi there! 🙆Just my 1 month at work !! I have not graduated yet, god, waiting for a diploma and graduation ceremony is too long." +
            "At the end of November 2020, it's my Graduation Ceremony, so cool, yeyeyehh 🙌🙌Look back to see what's cool ... haha ​​:)). Here I will summarize the past 1 month, short, not too long!",
          bodyContent:
            "Work started on October 19, 2020." +
            "Wake up at six o'clock " +
            "Preparing to go to work! " +
            "Take 2 bus routes to the company." +
            "My main job is to be on the hotline of the company and ... find customers to sell service charges, help customers send goods and documents to overseas, everyone calls Sales Logistics :)) 👀" +
            "Thought easy but not easy, neither difficult nor difficult! To do this job well, just be good at talking, moreover, having to understand the profession is too ok!💦" +
            "After 1 month, the job is also a little fine, no pressure, like when it started! Cute colleague, the boss is also cute! The brothers at the company cook lunch for employees to eat!" +
            "The special thing here is that the company I currently work for, everyone is in Hoai Nhon district, Binh Dinh province, all of them are their countrymen !! yeyeye ehh.💀💀" +
            "So, that's all!",
          endContent:
            "But try to have a full Tet!" +
            "It's going to be the Lunar New Year ~ so fast. A few months to go back to my hometown to welcome TET HOLIDAY 💥💥😘" +
            "It's over, thanks for watching, everyone fighting too hihi byeeee! 💭💗",
          createdDate: "14/11/2020",
        },
        {
          id: "002",
          title: "A LITTLE CONFESSION AT NIGHT !",
          image: "https://files.fm/thumb_show.php?i=5tgff2xzy",
          description: "Now that I am 22, I must have my plans. Of course,...",
          headContent:
            "Now that I am 22, I must have my plans. Of course, I always want to be the most perfect version and I'm working on it.😆 Do you know? This is the first time I do this- writing about myself on the blog. No problem, as long as I can feel comfortable. ^^ ok right! ☝☝",
          bodyContent:
            " So, I feel like myself when I write. Yah,  💛I write not for the sake of being published, for publication, or for being read by someone, but for the thrill of putting a pen on paper. I write for the love of what I create, for the sake of writing. Because in writing, I can see my thoughts more clearly. I write because there is something that needs to be liberated.  💜I wrote to temporarily leave the busy world and connect more deeply with myself. I write because there are things I know I shouldn't say. I write to be understood. 💚I wrote so as not to be forgotten. I write because my mind has so many ideas and to rearrange, I am forced to free them somehow. Nothing more than writing.",
          endContent:
            "So, do you want to know what I'll write about ?? Indeed, I want to write about all of the experiences in my life. It's too late right now, I'm writing a very rush some line about today. Suddenly, I feel lonely, I don't know why! I feel so lost. Maybe Cuz so long time, It's been a long time since I've forgotten what I want, what I need in the future, and I seem to forget how to look at myself... uh-huh! In a few more months, I'll graduate, cuz some reason, 😐it's make everything in my life temporarily delayed. 💨 A few times, I heard that there is a developed pathogen in China that's it, Nobody wants that to happen, not even me! That's unintended incidents! Until right now, I cant go to practice at my company! So bad, but it's nothing, I believe that everything will be alright! Also maybe for a long time, I don't have someone, who can share with me all of the things in life! Oh, my goodness, 😄😖wait, what I said, haha never mind, sometimes, I want to be like that, sometimes I don't even understand myself what I want!, I'm also want to find out someone, who can understand me, side by side me, cuz I'm just a girl, sometimes just weak, so I need a shoulder! It is often said that when a lonely adult will want to be alone, yes, but I can't be alone for too long, because that would freeze the soul.💤💋💋" +
            "Oops! I just remember one of the quotes, it's quiet, let me writing, this is  where there's a will there's a way right! yeyeee❤❤☝",
          createdDate: "03/04/2020",
        },
      ],
    };
  },

  methods: {
    clickShowPopupReadMore(idPost) {
      var _detail = this.detailPost;
      this.listPost.map(function (value, key) {
        if (idPost === value.id) {
          _detail.id = value.id || key;
          _detail.title = value.title;
          _detail.image = value.image;
          _detail.headContent = value.headContent;
          _detail.bodyContent = value.bodyContent;
          _detail.endContent = value.endContent;
          _detail.createdDate = value.createdDate;
        }
      });
      this.detailPost = _detail;
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

.card {
  margin-top: 10px;
}
</style>
