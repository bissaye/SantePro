<template>
  <div>
    <div class="main">
      <div class="line">
        <Bienvenue :userInfo="userinfos" />
        <Information :info="infos" />
      </div>
      <div class="line">
        <Services :serviceItem="servicesItem" />
        <Factures />
      </div>
    </div>
  </div>
</template>

<script>
import Bienvenue from "@/components/customCard/Bienvenue";
import Information from "@/components/customCard/Information";
import Services from "@/components/customCard/Services";
import Factures from "@/components/customCard/Factures";

export default {
  name: "Home",
  components: {
    Bienvenue,
    Information,
    Services,
    Factures,
  },
  data() {
    return {
      // datas for bienvenue components
      userinfos: [
        {
          RAISON: "RAISON SOCIALE",
          FINESS: "FINESS",
          RPPS: "RPPS",
          ADELI: "ADELI",
          SIRET: "SIRET",
          Adresse: "Adresse",
          Téléphone: "Telephone",
          Mail: "Mail",
          Divers: [{ divers: "divers 1" }, { divers: "divers 2" }],
        },
      ],

      // dats for informations components
      infos: [
        {
          logiciel: "LOGICIEL",
          concentrateur: "CONCENTRATEUR",
          banque: "BANQUE",
          IBAN: "IBAN",
          IBAN2: "IBAN TP",
        },
      ],

      // datas for service component
      servicesItem: [
        {
          title: "Recouvrement du tiers payant",
          active: true,
          list: [
            { text: "gestion et relance des organismes payeurs" },
            { text: "feed back d'un manager expert tiers payant" },
          ],
        },
        {
          title: "Base de connaissance santé plus",
          active: false,
          list: [
            { text: "Lorem ipsum dolor sit amet consectetur ad" },
            { text: "Lorem ipsum dolor sit amet consectetur ad" },
          ],
        },
        {
          title: "Mise en conformité du fichier organismes",
          active: true,
          list: [
            { text: "Codification d'une nomenclature" },
            { text: "Supression des doublons" },
            { text: "Correction des organismes mal renseignés" },
            { text: "mise à jour des contrats" },
          ],
        },
        {
          title: "Délégation du tiers payant",
          active: true,
          list: [
            { text: "Pointage des bordereaux de paiement" },
            { text: "Enregistrement des nouveaux organismes" },
            { text: "Feedback d'un manager expert tiers payant" },
            { text: "Traitement des rejets et recyclage des factures" },
            { text: "Gestion et relance des organismes payeurs" },
          ],
        },
        {
          title: "SantéBank et rapprochement bancaire 100% controlé",
          active: true,
          list: [
            { text: "Controler 100% des paiements en banque" },
            { text: "Sécuriser tous les paiements de tiers-payant" },
            { text: "Rapprocher 100% des FSE et organismes" },
          ],
        },
      ],
    };
  },
};
</script>

<style scoped>
.main {
  align-items: center;
}
.line {
  display: flex;
  flex-direction: row;
  align-items: flex-start;
  justify-content: center;
  flex-wrap: wrap;
}
</style>
