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
  <div class="p-3">
    <data-table-component />
  </div>
</template>

<script setup>
import DataTableComponent from "@/components/cash/DataTableComponent.vue";
</script>

<style></style>
