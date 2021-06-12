<template>
  <b-modal
    id="modal-lg"
    size="lg"
    :title="title"
    scrollable
    :lazy="isLazy"
    :no-close-on-backdrop="isNoClickBackdrop"
    centered
    :hide-header-close="isHideCloseButton"
    :ok-only="isOkOnly"
    ok-variant="success"
    ok-title="Done"
  >
    <b-row>
      <b-col sm="3" class="border-right-col">
        <img :src="image" class="card-img-top" />
        <hr class="my-2" />
        <i style="text-align: center">{{ createdDate }}</i>
      </b-col>
      <b-col>
        <p>{{ headContent }}</p>
        <hr class="my-4" />
        <p>{{ bodyContent }}</p>
        <hr class="my-4" />
        <p>{{ endContent }}</p>
      </b-col>
    </b-row>
  </b-modal>
</template>
<script>
export default {
  name: "PopupReadmore",
  props: ["title", "image", "headContent", "bodyContent", "endContent", "createdDate"],
  data() {
    return {
      isNoClickBackdrop: true,
      isOkOnly: true,
      isLazy: true,
      isHideCloseButton: true,
    };
  },
};
</script>
<style>
.border-right-col {
  border-right: 0.5px solid rgb(207, 177, 177);
  text-align: center;
}
p {
  font-family: Cambria, Cochin, Georgia, Times, "Times New Roman", serif;
}
h5.modal-title {
  font-family: Impact, Haettenschweiler, "Arial Narrow Bold", sans-serif;
  text-align: left;
  color: #a28089;
}

.modal-header {
  background-color: #51e2f5;
}
</style>
