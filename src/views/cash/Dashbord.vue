<template>
  <main class="d-flex flex-row">
    <div class="d-flex flex-column custom_nav" style="width: 250px">
      <div class="d-flex flex-column mt-5 ps-4">
        <div class="mb-2">
          <router-link to="/cash/avances/" class="nav-link">
            Details avances
          </router-link>
        </div>
        <div class="mb-2">
          <router-link to="/cash/impayes/" class="nav-link">
            Details impayé
          </router-link>
        </div>
        <div class="mb-2">
          <router-link to="/cash/details/" class="nav-link">
            Details
          </router-link>
        </div>
        <div class="mb-2"><a class="nav-link" href="">Rejet</a></div>
        <div class="mb-2"><a class="nav-link" href="">Contrat</a></div>
        <div class="mb-2"><a class="nav-link" href="">Support</a></div>
      </div>
    </div>
    <div style="width: 250px"></div>
    <div class="row custom-db-w">
      <div class="col-md-6 ps-5 pt-3">
        <div class="card p-2 pt-4">
          <div class="mb-4">
            <span class="p-2 fs-8 bg-black-10"
              ><i class="pi pi-calendar p5-1"></i> Période de recherche</span
            >
          </div>
          <div class="card p-3 mb-1">
            <div class="mb-4">
              <span class="fs-8">Montant télétransmis</span>
              <div class="progress">
                <div
                  class="progress-bar text-black"
                  role="progressbar"
                  style="width: 100%; background-color: #82d9e8"
                  aria-valuenow="100"
                  aria-valuemin="0"
                  aria-valuemax="100"
                >
                  20.000 euro
                </div>
              </div>
            </div>

            <div class="mb-1">
              <span class="fs-8">Montant avancé</span>
              <div class="progress">
                <div
                  class="progress-bar text-black"
                  role="progressbar"
                  style="width: 93%; background-color: #79db79"
                  aria-valuenow="93"
                  aria-valuemin="0"
                  aria-valuemax="100"
                >
                  18 000 euro
                </div>
              </div>
            </div>
          </div>
          <div class="card p-3">
            <div class="mb-4">
              <span class="fs-8">Payé par les organismes</span>
              <div class="progress">
                <div
                  class="progress-bar text-black"
                  role="progressbar"
                  style="width: 90%; background-color: #f5e69a"
                  aria-valuenow="25"
                  aria-valuemin="0"
                  aria-valuemax="100"
                >
                  90%
                </div>
              </div>
            </div>
            <div class="mb-4">
              <span class="fs-8">En attente de paiement</span>
              <div class="progress">
                <div
                  class="progress-bar text-black"
                  role="progressbar"
                  style="width: 10%; background-color: #faddb9"
                  aria-valuenow="25"
                  aria-valuemin="0"
                  aria-valuemax="100"
                >
                  10%
                </div>
              </div>
            </div>
            <div class="mb-4">
              <span class="fs-8">Taux de rapprochement éffectué</span>
              <div class="progress" style="height: 30px">
                <div
                  class="progress-bar text-black"
                  role="progressbar"
                  style="width: 92%; background-color: #f5bfcc"
                  aria-valuenow="25"
                  aria-valuemin="0"
                  aria-valuemax="100"
                >
                  92%
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="col-md-6 pt-3">
        <div class="card p-2 pt-2">
          <div class="text-center">
            <span class="text-center fw-bold fs-5">IMPAYES</span>
          </div>
          <div class="d-flex flex-column justify-content-center mt-1">
            <div style="width: 400px" class="text-center align-self-center">
              <PieChart :chartData="chartData2" :lightOptions="lightOptions2" />
            </div>
            <div style="width: 400px" class="text-center align-self-center">
              <PieChart :chartData="chartData1" :lightOptions="lightOptions1" />
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<script setup>
import { ref } from "@vue/reactivity";
import PieChart from "@/components/cash/PieChart.vue";

const chartData1 = ref({
  labels: ["Motif1", "Motif2", "Motif3", "Motif4", "Motif5", "Motif6"],
  datasets: [
    {
      data: [30, 50, 25, 60, 40, 12],
      backgroundColor: [
        "#c5648e",
        "#e1f28c",
        "#8fd2d5",
        "#86c988",
        "#c383ad",
        "#ddce96",
      ],
      hoverBackgroundColor: [
        "#b95882",
        "#c8d876",
        "#86c6c9",
        "#72b774",
        "#b679a1",
        "#c3b683",
      ],
    },
  ],
});

const lightOptions1 = ref({
  plugins: {
    legend: {
      labels: {
        color: "#495057",
      },
    },
  },
});

const chartData2 = ref({
  labels: ["Impayé à j-60", "Impayé à j+60"],
  datasets: [
    {
      data: [30, 50],
      backgroundColor: ["#c5648e", "#e1f28c"],
      hoverBackgroundColor: ["#b95882", "#c8d876"],
    },
  ],
});

const lightOptions2 = ref({
  plugins: {
    legend: {
      labels: {
        color: "#495057",
      },
    },
  },
});
</script>

<style>
.custom_nav {
  position: fixed;
  height: 100vh;
  background: rgb(229, 229, 234);
}

.custom-db-w {
  width: calc(100% - 250px);
}

.fs-8 {
  font-size: 12px;
}

.nav-link {
  color: rgb(70, 70, 70);
}

.bg-black-10 {
  background: rgb(227, 227, 227);
}

.progress {
  height: 30px;
  border-radius: 40px;
}
.progress > div {
  border-radius: 40px;
}
</style>
