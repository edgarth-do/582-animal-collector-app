<template>
  <div class="animalCollector">
    <div id="div1">
      <h3>{{ collection.feature }}</h3>
    </div>
    <div id="div2">
      <img :src="collection.photo" :alt="collection.animalName" />
    </div>
    <button id="btn" @click="isCollect(collection.id, collection.animalName)">
      <img v-if="!collect" src="../assets/collen.png" alt="Collected" />
      <img v-else src="../assets/collec.png" alt="Replace" />
    </button>
    <div id="div4">
      <p>{{ collection.habitat }}</p>
    </div>
    <div id="div5">
      <h2>{{ collection.animalName }}</h2>
    </div>
    <div id="div6">
      <p>{{ collection.description }}</p>
    </div>
    <div id="div7">
      <h2>{{ collection.age }}</h2>
    </div>
    <div id="div8">
      <h3>{{ collection.weight }}</h3>
    </div>
    <div id="div9">
      <h4>{{ collection.measures }}</h4>
    </div>
    <button id="btn2" class="share-button" @click="shareOnInstagram">
      <img src="../assets/instagram.png" alt="Share" />
    </button>
  </div>
</template>

<script>
export default {
  name: "animalData",
  props: {
    collection: {
      type: Object,
      required: true,
    },
  },

  data() {
    return {
      collect: false,
      share: false,
    };
  },

  methods: {
    isCollect(id, animalName) {
      this.collect = !this.collect;
      this.$emit("addCollection", id);
      console.log("Already collected...", animalName);
    },
    shareOnInstagram() {
      const instagramUrl = `https://www.instagram.com`;
      window.open(instagramUrl, "_blank");
    },
  },
};
</script>

<style scoped lang="scss">
.animalCollector {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-template-rows: repeat(5, 1fr);
  grid-column-gap: 12px;
  grid-row-gap: 12px;
  margin: 0 auto;
  padding: 15px;

  p {
    font-family: "Aleo", serif;
  }

  #btn,
  #btn2 {
    background: none;
    border: none;
    color: none;
  }

  #btn img,
  #btn2 img {
    width: 45px;
    border-radius: 9px;

    &:hover {
      width: 45px;
      box-shadow: 1px 1px 4px #f9fadf;
    }
  }
}

#div1 {
  grid-area: 1 / 1 / 3 / 2;
}
#div2 {
  grid-area: 1 / 2 / 3 / 4;
  img {
    border-radius: 50px;
  }
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
