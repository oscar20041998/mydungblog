<template>
  <b-modal id="modal-lg" size="lg" title="Large Modal">{{ title }}</b-modal>
</template>
<script>
export default {
  name: "PopupReadmore",
  props: ["tilte", "image", "content"],
};
</script>
<style scoped></style>
