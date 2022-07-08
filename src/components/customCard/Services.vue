<template>
  <div class="custom-card">
    <h3>
      <i class="fa-solid fa-file" style="color: #007bff"></i>
      Vos Services
    </h3>
    <div class="service-content">
      <div v-for="item in servicesItem" :key="item">
        <div class="card sm-2" style="width: 20rem; margin-bottom: 10px">
          <div class="card-body">
            <h6 class="card-subtitle">{{ item.title }}</h6>
            <div v-if="item.active">
              <p class="card-text"></p>
              <div v-for="items in item.list" :key="items">
                <i class="fa-solid fa-check" style="color: green"></i>
                {{ items.text }} <br />
              </div>
              <p style="color: green">
                <i class="fa-solid fa-square-check" style="color: green"></i>
                Service activé
              </p>
            </div>

            <div v-else>
              <p class="card-text"></p>
              <div v-for="items in item.list" :key="items">
                <i class="fa-solid fa-xmark" style="color: orange"></i>
                {{ items.text }} <br />
              </div>
              <p style="color: orange">
                <i
                  class="fa-solid fa-triangle-exclamation"
                  style="color: orange"
                ></i>
                Service désactivé
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Services",
  props: ["serviceItem"],
  data() {
    return {
      servicesItem: this.serviceItem,
    };
  },
};
</script>

<style scoped>
.custom-card {
  width: 700px;
  overflow: hidden;
  transition: 1s ease-in-out;
  transform-style: preserve-3d;
  animation: custom-flip;
  animation-duration: 4s;
}
@keyframes custom-flip {
  0% {
    transform: rotateY(0.5turn);
  }
  100% {
    transform: rotateY(0turn);
  }
}
.service-content {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-evenly;
}
</style>
