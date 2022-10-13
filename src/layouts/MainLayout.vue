<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated class="header-toolbar">
      <h2 class="header-toolbar is-4">
        <i class="fa fa-home"></i><b>habitação</b>.caixa
      </h2>
    </q-header>

    <q-page-container>
      <q-breadcrumbs class="text-orange page-bar" active-color="secondary">
        <q-breadcrumbs-el
          ><a href="http://habitacao.caixa">Home</a></q-breadcrumbs-el
        >
        <q-breadcrumbs-el>Indices Operacionais</q-breadcrumbs-el>
      </q-breadcrumbs>
      <h3 class="text-warning text-h4 text-wheight-bold titulo">
        Indices Operacionais
      </h3>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from "vue";

export default defineComponent({
  name: "MainLayout",

  components: {},

  setup() {
    return {};
  },
});
</script>

<style scoped>
.page-bar {
  background-color: #ffffff;
  position: relative;
  font-family: futura-lt-book, "Helvetica Neue", Helvetica, Arial, sans-serif;
  line-height: 1.42857;
  color: #333;
  -webkit-font-smoothing: antialiased !important;
}
.header-toolbar {
  width: 100%;
  box-shadow: none;
  filter: none;
  background-image: none;
  background: linear-gradient(270deg, #54bbab, #0052a9) !important;
  border-top: 1px solid #19578a !important;
  border-bottom: 2px solid #f7941e !important;
  font-family: futura-lt-book, "Helvetica Neue", Helvetica, Arial, sans-serif !important;
  color: #ffffff;
  display: flex;
}
.fa-home {
  margin-top: 10px;
  display: inline-block;
  box-sizing: border-box;
  margin-left: 5px;
  margin-right: 10px;
}
.header-text {
  margin-left: 13px;
}
h2 {
  font-size: 33px !important;
}
.titulo {
  margin-top: 10px;
}
</style>
