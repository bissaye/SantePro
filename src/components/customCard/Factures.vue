<template>
  <div class="custom-card">
    <h3>
      <i class="fa-solid fa-euro-sign" style="color: #007bff"></i>
      Vos Factures
    </h3>
    <h4>Année en cours</h4>
    <ul class="mois-list">
      <li v-for="item in mois" :key="item">
        <div style="color: #007bff">{{ item }} {{ year }}</div>
      </li>
    </ul>
    <router-link to="/Contact" type="button" class="btn btn-secondary modifier">
      changer de période
    </router-link>
  </div>
</template>

<script>
export default {
  name: "Factures",
  data() {
    return {
      year: 2022,
      mois: [
        "janvier",
        "fevrier",
        "mars",
        "avril",
        "mai",
        "juin",
        "juillet",
        "aout",
        "septembre",
        "octobre",
        "novembre",
        "decembre",
      ],
    };
  },
};
</script>

<style scoped>
.custom-card {
  width: 700px;
  height: 670px;
  overflow: scroll;
  transition: 1s ease-in-out;
  transform-style: preserve-3d;
  animation: custom-flip;
  animation-duration: 2s;
}
@keyframes custom-flip {
  0% {
    transform: rotateY(0.5turn);
  }
  100% {
    transform: rotateY(0turn);
  }
}
h4 {
  margin: 30px;
  font-size: medium;
}
.mois-list {
  list-style: none;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-around;
}

.mois-list li {
  background-color: rgb(236, 236, 236);
  text-align: left;
  border: solid black 1px;
  width: 50%;
  padding: 5px;
}
</style>
