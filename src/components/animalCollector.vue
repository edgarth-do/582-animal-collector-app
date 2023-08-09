<template>
  <h2>Animal Collector app</h2>
  <div class="animal-feature">
    <div class="dropdown">
      <button onclick="displayList()" class="dropbtn">Features</button>
      <div id="selection" class="features">
        <a href="#hunt">hunt</a>
        <a href="#domestic">domestic</a>
        <a href="#acuatic">acuatic</a>
      </div>
    </div>
  </div>
</template>

<script>
function displayList() {
  document.getElementById("selection").classList.toggle("show");
}
</script>
