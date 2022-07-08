<template>
  <div class="custom-card">
    <h4>
      <i class="fa-solid fa-user" style="color: #007bff"></i>
      Bienvenue dans votre espace client
    </h4>
    <h3>
      {{ userInfos[0].RAISON }}
    </h3>
    <P>
      {{ userInfos[0].FINESS }}/ {{ userInfos[0].RPPS }}/
      {{ userInfos[0].ADELI }} <br />
      {{ userInfos.SIRET }}
    </P>
    <P>
      {{ userInfos[0].Adresse }} <br />
      {{ userInfos[0].Téléphone }}<br />
      {{ userInfos[0].Mail }}<br />
      <div v-for="item in userInfos[0].Divers" :key="item">
        {{ item.divers }}
      </div>
    </P>
    <router-link to="/Contact" type="button" class="btn btn-secondary modifier">
      modifier
    </router-link>
  </div>
</template>

<script>
export default {
  name: "Bienvenue",
  props: ["userInfo"],
  data() {
    return {
      userInfos: this.userInfo,
    };
  },
};
</script>

<style scoped>
h3 {
  text-align: center;
}
.custom-card {
  height: 250px;
  width: 700px;
  overflow: hidden;
  transition: 1s ease-out;
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
