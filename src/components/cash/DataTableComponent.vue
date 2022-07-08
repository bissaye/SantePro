<template>
  <div>
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
      <Column :expander="true" headerStyle="width: 3rem">test</Column>
      <Column field="date_avance" header="Date de l'avance" sortable>
        <template #body="slotProps">
          {{ slotProps.data.date_avance }}
        </template>
      </Column>
      <Column field="montant_virement" header="Montant du virement">
        <template #body="slotProps">
          {{ slotProps.data.montant_virement }}
        </template>
      </Column>
      <Column field="montant_avance" header="Montant avancé">
        <template #body="slotProps">
          {{ slotProps.data.montant_avance }}
        </template>
      </Column>
      <Column field="montant_regularise" header="Montant regularisé">
        <template #body="slotProps">
          {{ slotProps.data.montant_regularise }}
        </template>
      </Column>
      <Column field="montant_hors_TP" header="Montant hors TP">
        <template #body="slotProps">
          {{ slotProps.data.montant_hors_TP }}
        </template>
      </Column>
      <template #expansion="slotProps">
        <div class="collapseTable" style="background: white">
          <DataTable
            :value="slotProps.data.sous_donnees"
            responsiveLayout="scroll"
            :paginator="true"
            :rows="10"
            paginatorTemplate="RowsPerPageDropdown FirstPageLink PrevPageLink PageLinks NextPageLink LastPageLink CurrentPageReport"
            :rowsPerPageOptions="[10, 20, 50]"
            currentPageReportTemplate="{first}-{last} de {totalRecords}"
          >
            <Column
              field="date_reception_facture"
              header="Date reception facture"
              sortable
            ></Column>
            <Column
              field="reception_facture"
              header="Reception facture"
              sortable
            ></Column>
            <Column field="type" header="Type" sortable></Column>
            <Column field="organisme" header="Organisme" sortable></Column>
            <Column field="montant_avance" header="Montant avancé" sortable>
            </Column>
            <Column
              field="montant_paye_organisme"
              header="Montant payé par l'organisme"
              sortable
            ></Column>
            <Column
              field="montant_regularisation"
              header="Montant régularisation"
              sortable
            ></Column>
            <Column
              field="date_regularisation"
              header="Date de régularisation"
              sortable
            ></Column>
            <Column
              field="status_rejet"
              header="Status rejet"
              sortable
            ></Column>
            <Column
              field="externalisation"
              header="Externalisation"
              sortable
            ></Column>
          </DataTable>
        </div>
      </template>
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
    date_avance: "testes",
    montant_virement: "10.000",
    montant_avance: "9.000",
    montant_regularise: "7.000",
    montant_hors_TP: "5000",
    sous_donnees: [
      {
        id: 1,
        date_reception_facture: "kqjhdsq",
        reception_facture: "qsdqsd",
        type: "qsdqsd",
        organisme: "qsdqsd",
        montant_avance: "qsdqsd",
        montant_paye_organisme: "qsdqsd",
        montant_regularisation: "qsdqsd",
        date_regularisation: "qsdqsd",
        status_rejet: "qsdqsd",
        externalisation: "qsdqsd",
      },
    ],
  },
  {
    id: 2,
    date_avance: "testes",
    montant_virement: "10.000",
    montant_avance: "9.000",
    montant_regularise: "7.000",
    montant_hors_TP: "5000",
    sous_donnees: [],
  },
];
</script>

<style></style>
