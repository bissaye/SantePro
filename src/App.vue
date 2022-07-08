<template>
  <nav-bar></nav-bar>
</template>

<script>
// @ is an alias to /src
import NavBar from "@/components/layouts/NavBar.vue";

export default {
  name: "Home",
  components: {
    NavBar,
  },
};
</script>

<style>
@import "./assets/css/app.css";

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}

.p-paginator {
  justify-content: end !important;
}

.collapseTable > .p-datatable .p-datatable-tbody > tr > td {
  background: white;
}

.p-datatable .p-datatable-tbody > tr > td {
  padding: 0px 1px !important;
  background: rgb(237, 237, 237);
}
.p-datatable .p-datatable-thead > tr > th {
  background: none !important;
}

.p-datatable .p-paginator-bottom {
  border-width: 0px;
}

.p-datatable .p-datatable-header {
  background: none;
  border-width: 0px 0px 1px 0px;
}
.input-group-text {
  background: none !important;
  border-width: 0px 0px 1px 0px !important;
  border-color: rgb(175, 175, 175) !important;
}
.custom_input {
  border-color: rgb(175, 175, 175) !important;
  border-width: 0px 0px 1px 0px !important;
}

.custom_input:focus {
  outline: none !important;
}

.btn {
  border-radius: 1px !important;
}

.block_btn {
  border-width: 1px 1px 1px 1px;
  border-style: solid;
  padding: 10px 7px 10px 7px;
  border-color: rgb(175, 175, 175);
}

.custom_card {
  padding: 1px;
}

.custom_card-green {
  background: #c5f5c5;
}
.custom_card-blue {
  background: #a4e6eb;
}
.input-group-text {
  background: none;
  border-width: 0px 0px 1px 0px;
  border-color: rgb(175, 175, 175);
}
.custom_input {
  border-color: rgb(175, 175, 175);
  border-width: 0px 0px 1px 0px;
}

.custom_input:focus {
  outline: none;
}

.btn {
  border-radius: 1px !important;
}

.block_btn {
  border-width: 1px 1px 1px 1px;
  border-style: solid;
  padding: 10px 7px 10px 7px;
  border-color: rgb(175, 175, 175);
}
</style>
