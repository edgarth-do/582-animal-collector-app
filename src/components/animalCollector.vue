<template>
  <!-- <h2>Animal Collector app</h2> -->
  <div class="collection">
    <div id="div1">
      <h4>{{ collection.feature }}</h4>
    </div>
    <div id="div2">
      <img :src="collection.photo" :alt="collection.animalName" />
    </div>
    <button
      id="btn"
      @click="addCollection(collection.id, collection.animalName)"
    >
      Collected
    </button>
    <div id="div4">
      <p>{{ collection.habitat }}</p>
    </div>
    <div id="div5">
      <h3>{{ collection.animalName }}</h3>
    </div>
    <div id="div6">
      <p>{{ collection.description }}</p>
    </div>
    <div id="div7">
      <p>{{ collection.age }}</p>
    </div>
    <div id="div8">
      <p>{{ collection.weight }}</p>
    </div>
    <div id="div9">
      <p>{{ collection.measures }}</p>
    </div>
    <button
      id="btn2"
      :class="{ isShared }"
      v-if="!isShared"
      @click="shared(collection.animalName)"
    >
      Shared!
    </button>
  </div>
</template>

<script>
// import AnimalData from "./animalData.vue";

export default {
  name: "animalCollector",
  props: {
    collection: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {
      isShared: false,
    };
  },
  methods: {
    addCollection(id, animalName) {
      this.$emit("addCollection", id);
      console.log("Already collected...", id, animalName);
    },
    share(animalName) {
      this.isShared = true;
      this.$emit("share", animalName);
    },
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

#div1 {
  grid-area: 1 / 1 / 3 / 2;
}
#div2 {
  grid-area: 1 / 2 / 3 / 4;
}
#btn {
  grid-area: 1 / 4 / 2 / 5;
}
#div4 {
  grid-area: 2 / 4 / 3 / 5;
}
#div5 {
  grid-area: 3 / 1 / 4 / 5;
}
#div6 {
  grid-area: 4 / 1 / 5 / 5;
}
#div7 {
  grid-area: 5 / 1 / 6 / 2;
}
#div8 {
  grid-area: 5 / 2 / 6 / 3;
}
#div9 {
  grid-area: 5 / 3 / 6 / 4;
}
#btn2 {
  grid-area: 5 / 4 / 6 / 5;
}
</style>
