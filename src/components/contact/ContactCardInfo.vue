<template>
  <div>
    <div class="info">
      <div
        class="card sm-2 text-center custom-card-contact"
        style="width: 20rem; margin-bottom: 10px; color: #007bff"
      >
        <div class="card-body">
          <h5 class="card-title">
            {{ this.infos[0].title }}
          </h5>
          <p class="card-text"></p>
          <div class="text-card-info">
            {{ this.infos[0].text }}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ContactCardInfo",
  props: ["info"],
  data() {
    return {
      infos: this.info,
    };
  },
};
</script>

<style scoped>
.text-card-info {
  color: black;
}
.custom-card-contact {
  transition: 1s ease-in-out;
  transform-style: preserve-3d;
  animation: custom-flip;
  animation-duration: 1s;
}
@keyframes custom-flip {
  0% {
    transform: rotateY(0.5turn);
  }
  100% {
    transform: rotateY(0turn);
  }
}
</style>
