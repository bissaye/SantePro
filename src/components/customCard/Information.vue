<template>
  <div class="custom-card">
    <h4>
      <i class="fa-solid fa-circle-info"></i>
      informations métier
    </h4>
    <h3></h3>
    <P>
      {{ infos[0].logiciel }} <br />
      {{ infos[0].concentrateur }}
    </P>
    <P>
      {{ infos[0].banque }} <br />
      {{ infos[0].IBAN }} <br />
      {{ infos[0].IBAN2 }} <br />
    </P>
    <router-link to="/Contact" type="button" class="btn btn-secondary modifier">
      modifier
    </router-link>
  </div>
</template>

<script>
export default {
  name: "Information",
  props: ["info"],
  data() {
    return {
      infos: this.info,
    };
  },
};
</script>

<style scoped>
.custom-card {
  height: 250px;
  width: 700px;
  overflow: hidden;
  transition: 1s ease-in-out;
  transform-style: preserve-3d;
  animation: custom-flip;
  animation-duration: 3s;
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
