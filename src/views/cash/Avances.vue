<template>
  <div class="d-flex mt-3 justify-content-between mb-4 align-items-center">
    <div>
      <button class="btn btn-outline-info me-1">Filtrer par date</button
      ><span class="text-black-50 fw-bold">date de démarage des ouvertures</span
      ><span class="text-black-50"> : 01/01/2000</span>
    </div>
    <div class="d-flex align-items-center">
      <div class="me-4">
        <button class="btn btn-outline-success">Extraire les avances</button>
      </div>
      <div class="block_btn me-4">
        <div class="input-group p-2">
          <input
            type="text"
            class="custom_input"
            placeholder="Rechercher une facture"
          />
          <span class="input-group-text" id="basic-addon2"
            ><i class="pi pi-search"
          /></span>
        </div>
      </div>
      <div class="block_btn me-4 text-black-50 text-center">
        <span>Crédit externalisation restant : 0</span><br />
        <span><a href="">Acheter des crédits</a></span>
      </div>
    </div>
  </div>
  <div class="row">
    <div class="col-md-8">
      <data-table-component />
    </div>
    <div class="col-md-4 pt-3 ps-2">
      <div class="row pt-5 justify-content-around">
        <div
          class="custom_card custom_card-green col-5 text-black-50 text-center"
        >
          <span>Crédit externalisation restant : 0</span><br />
          <span>Acheter des crédits</span>
        </div>
        <div
          class="custom_card custom_card-blue col-5 text-black-50 text-center"
        >
          <span>Crédit externalisation restant : 0</span><br />
          <span>Acheter des crédits</span>
        </div>
      </div>
      <div class="d-flex justify-content-around mt-5">
        <div style="width: 400px" class="text-center">
          <span class="fw-bold">Facture 60 derniers jours</span>
          <PieChart :chartData="chartData1" :lightOptions="lightOptions1" />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import DataTableComponent from "@/components/cash/DataTableComponent.vue";
import { ref } from "@vue/reactivity";
import PieChart from "@/components/cash/PieChart.vue";

const chartData1 = ref({
  labels: ["Montant non payé", "Montant payé", "Hors tiers payant"],
  datasets: [
    {
      data: [30, 200, 10],
      backgroundColor: ["#ebdf83", "#acd2d9", "#b5b5b3"],
      hoverBackgroundColor: ["#d1c35f", "#79adb6", "#969696"],
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
</script>

<style></style>
