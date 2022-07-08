<template>
  <div class="ps-3">
    <DataTable
      :value="datas"
      dataKey="id"
      v-model:expandedRows="expandedRows"
      responsiveLayout="scroll"
      :paginator="true"
      :rows="10"
      paginatorTemplate="RowsPerPageDropdown FirstPageLink PrevPageLink PageLinks NextPageLink LastPageLink CurrentPageReport"
      :rowsPerPageOptions="[10, 20, 50]"
      currentPageReportTemplate="{first}-{last} de {totalRecords}"
    >
      <Column field="date_facture" header="Date de la facture" sortable>
        <template #body="slotProps">
          {{ slotProps.data.date_facture }}
        </template>
      </Column>
      <Column field="montant_total" header="Montant Total">
        <template #body="slotProps">
          {{ slotProps.data.montant_total }}
        </template>
      </Column>
      <Column field="montant_impaye" header="Montant impayé">
        <template #body="slotProps">
          {{ slotProps.data.montant_impaye }}
        </template>
      </Column>
      <Column field="type_organisme" header="Montant organisme">
        <template #body="slotProps">
          {{ slotProps.data.type_organisme }}
        </template>
      </Column>
      <Column field="orginisme" header="Orginisme">
        <template #body="slotProps">
          {{ slotProps.data.orginisme }}
        </template>
      </Column>
      <Column field="motif_impaye" header="Motif impayé">
        <template #body="slotProps">
          {{ slotProps.data.motif_impaye }}
        </template>
      </Column>
      <Column field="motif_rejet" header="Motif rejet">
        <template #body="slotProps">
          {{ slotProps.data.motif_rejet }}
        </template>
      </Column>
    </DataTable>
  </div>
</template>

<script setup>
import { ref } from "@vue/reactivity";
import DataTable from "primevue/datatable";
import Column from "primevue/column";
const datas = ref();
const expandedRows = ref([]);
datas.value = [
  {
    id: 1,
    date_facture: "testes",
    montant_total: "10.000",
    montant_impaye: "9.000",
    type_organisme: "7.000",
    orginisme: "7.000",
    motif_impaye: "7.000",
    motif_rejet: "5000",
  },
  {
    id: 1,
    date_facture: "testes",
    montant_total: "10.000",
    montant_impaye: "9.000",
    type_organisme: "7.000",
    orginisme: "7.000",
    motif_impaye: "7.000",
    motif_rejet: "5000",
  },
  {
    id: 1,
    date_facture: "testes",
    montant_total: "10.000",
    montant_impaye: "9.000",
    type_organisme: "7.000",
    orginisme: "7.000",
    motif_impaye: "7.000",
    motif_rejet: "5000",
  },
  {
    id: 1,
    date_facture: "testes",
    montant_total: "10.000",
    montant_impaye: "9.000",
    type_organisme: "7.000",
    orginisme: "7.000",
    motif_impaye: "7.000",
    motif_rejet: "5000",
  },
  {
    id: 1,
    date_facture: "testes",
    montant_total: "10.000",
    montant_impaye: "9.000",
    type_organisme: "7.000",
    orginisme: "7.000",
    motif_impaye: "7.000",
    motif_rejet: "5000",
  },
  {
    id: 1,
    date_facture: "testes",
    montant_total: "10.000",
    montant_impaye: "9.000",
    type_organisme: "7.000",
    orginisme: "7.000",
    motif_impaye: "7.000",
    motif_rejet: "5000",
  },
  {
    id: 1,
    date_facture: "testes",
    montant_total: "10.000",
    montant_impaye: "9.000",
    type_organisme: "7.000",
    orginisme: "7.000",
    motif_impaye: "7.000",
    motif_rejet: "5000",
  },
  {
    id: 1,
    date_facture: "testes",
    montant_total: "10.000",
    montant_impaye: "9.000",
    type_organisme: "7.000",
    orginisme: "7.000",
    motif_impaye: "7.000",
    motif_rejet: "5000",
  },
];
</script>

<style scoped>
.p-datatable .p-datatable-tbody > tr > td {
  padding: 0px 1px !important;
  background: rgb(255, 255, 255);
}
</style>
