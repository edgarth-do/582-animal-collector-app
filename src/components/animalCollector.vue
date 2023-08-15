<!--<template>
  
   <div class="collection">
    <div id="div1">
      <h4>{{ collection.feature }}</h4>
    </div>
    <div id="div2">
      <img :src="collection.photo" :alt="collection.animalName" />
    </div>
    <button id="btn" @toggleCollect(collection.id, collection.animalName)">
      <img v-if="!collect" src="../assets/collen.png" alt="Collect" />
      <img v-else src="../assets/collec.png" alt="Collected" />
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
      @click="share(collection.animalName)"
    >
      <a :href="instaLink" target="_blank">
        <img src="../assets/instagram.png" alt="Share" />
      </a>
    </button>
  </div>
</template>

<script>
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
      collect: false,
      
    };
  },
  computed: {
    instaLink() {
      return `https://www.instagram.com/${this.collection.animalName}/`;
    },
  },
  methods: {
    toggleCollect(id, animalName) {
      this.collect = !this.collect;
      this.$emit("addCollection", id);
      console.log("Already collected...", id, animalName);
    },
    isShare(animalName) {
      console.log(`Sharing ${animalName} on Instagram`);
    },
  },
}; 
</script>-->
