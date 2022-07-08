<template>
  <div>
    <div class="info">
      <div v-for="item in infos" :key="item">
        <ContactCardInfo :info="item" />
      </div>
    </div>
    <div class="custom-form">
      <h4>FORMULAIRE DE CONTACT</h4>
      <form class="form">
        <div id="input-group-1" class="form-group col-md-5">
          <select class="form-select" id="input-1" v-model="form.categorie">
            <option selected value="null">Catégorie</option>
            <option v-for="item in categories" :key="item" :value="item.value">
              {{ item }}
            </option>
          </select>
        </div>

        <div id="input-group-2" class="col-md-5 form-group">
          <select class="form-select" id="input-2" v-model="form.sujet">
            <option selected value="null">Sujet</option>
            <option v-for="item in sujets" :key="item" :value="item.value">
              {{ item }}
            </option>
          </select>
        </div>

        <div class="form-group" id="input-group-3">
          <textarea
            class="form-textarea"
            id="textarea"
            v-model="text"
            placeholder="Message"
            rows="10"
            cols="100"
            max-rows="6"
          >
          </textarea>
        </div>

        <div class="form-group" id="input-group-4">
          <label for="checkboxes-4" class="form-check-label">
            Par quel moyen souhaitez vous etre recontacté
          </label>

          <div
            class="form-checkbox-group"
            id="checkboxes-4"
            aria-describedby="ariaDescribedby"
          >
            <label for="form-check-Téléphone" class="form-check-label"
              >Téléphone &nbsp;
            </label>
            <input
              type="checkbox"
              class="form-checkbox"
              id="form-check-Téléphone"
              value="Téléphone"
              v-model="form.telCheck"
            />
            &nbsp;

            <label for="form-check-E-mail" class="form-check-label"
              >E-mail &nbsp;
            </label>
            <input
              type="checkbox"
              class="form-checkbox"
              id="form-check-E-mail"
              value="E-mail"
              v-model="form.mailCheck"
            />
            &nbsp;

            <input
              type="text"
              name=""
              id="input3"
              placeholder="Insérer contact ici"
              v-model="form.contact"
              class="form-input col-md-5"
              :disabled="ContactCheck"
            />
          </div>
        </div>

        <div class="custom-file" id="customFile">
          <i class="fa-solid fa-paperclip"></i><input type="file" />
        </div>

        <button
          type="submit"
          variant="primary"
          style="background-color: green"
          class="modifier"
        >
          Envoyer
        </button>
      </form>
    </div>
  </div>
</template>

<script>
import ContactCardInfo from "@/components/contact/ContactCardInfo.vue";
export default {
  name: "Contact",
  components: {
    ContactCardInfo,
  },
  data() {
    return {
      infos: [
        [{ title: "15", text: "Cas ouverts avec santépros" }],
        [{ title: "13", text: "Cas traités et fermés par santépros" }],
        [{ title: "3", text: "Cas ouverts avec santépros" }],
        [{ title: "4 heures", text: "Temps moyen de traitement" }],
      ],
      form: {
        categorie: null,
        sujet: null,
        telCheck: null,
        mailCheck: null,
        contact: null,
      },

      categories: [
        "Administratif",
        "Commercial",
        "Service Technique",
        "Problème flux ( sb seulement )",
        "Divers",
      ],
      file1: null,
    };
  },
  computed: {
    sujets() {
      if (this.form.categorie === this.categories[1]) {
        return ["Changement de RIB", "Changement d'adresse"];
      } else if (this.form.categorie === this.categories[2]) {
        return [
          "Questioin contrat",
          "Question facturation",
          "Adhésion nouveau service",
        ];
      } else if (this.form.categorie === this.categories[3]) {
        return ["Bug interface", "Changement de mail de correction"];
      } else if (
        this.form.categorie === this.categories[4] ||
        this.form.categorie === this.categories[5]
      ) {
        return ["Problème de remonté facture", "Problème de flux"];
      } else {
        return [];
      }
    },
    ContactCheck() {
      if (this.form.telCheck || this.form.mailCheck) {
        return false;
      } else {
        return true;
      }
    },
  },
};
</script>

<style scoped>
.info {
  margin-top: 30px;
  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
  align-items: center;
}
.custom-form {
  padding: 20px;
  display: flex;
  align-items: center;
  flex-direction: column;
}

.modifier {
  margin-top: 10px;
  margin-left: 90%;
}

.form-group {
  margin-bottom: 10px;
}
#input3 {
  margin-left: 35%;
}
#customFile {
  margin-left: 80%;
  transform: translateX(-50%);
  padding: 1px;
  width: 320px;
}
</style>
