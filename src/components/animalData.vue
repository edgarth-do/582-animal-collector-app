<template>
  <div class="animalCollector">
    <div id="1" {{collection.feature}}></div>
    <div id="2">{{ collection.photo }}</div>
    <button id="3" :class="{ isCollected }" v-if="visible" @click="action">
      Collected!
    </button>
    <div id="4">{{ collection.collected }}</div>
    <div id="5">{{ collection.habitat }}</div>
    <div id="6">{{ collection.animalName }}</div>
    <div id="7">{{ collection.descrption }}</div>
    <div id="8">{{ collection.age }}</div>
    <div id="9">{{ collection.measures }}</div>
    <button id="btn2" :class="{ isShared }" v-if="share" @click="share">
      Liked!
    </button>
  </div>
</template>

<script>
export default {
  name: "animalCollector",
  props: {
    collection: {
      type: Object,
      default() {
        return {
          id: 1,
          feature: "feature",
          photo: "https://placehold.co/185*185",
          habitat: "habitat",
          animalName: "animalName",
          description:
            "Neque porro quisquam est qui dolorem ipsumquia dolor sit amet, consectetur, adipisci velit.",
          age: 0,
          weight: "weight",
          measures: "measures",
          share: "Share",
        };
      },
    },
  },
  action() {
    this.isClicked = true;
    this.$emit("action", true.isCollected);
    this.addCollection = true;
  },
  share() {
    this.isShared = true;
    this.$emit("share", true.isShared);
    this.addCollection = true;
  },
};
</script>

<style scoped lang="scss">
.collection {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-template-rows: repeat(5, 1fr);
  grid-column-gap: 12px;
  grid-row-gap: 12px;
}
</style>
