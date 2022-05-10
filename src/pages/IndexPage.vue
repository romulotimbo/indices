<template>
  <q-page padding>
    <div class="q-pa-md">
      <div class="columns">
        <div class="column is-3">
          <q-select
            label="Controladoras"
            v-model="controladora"
            :options="optionsControladoras"
          >
          </q-select>
        </div>
        <div class="column is-2">
          <q-select
            label="Produto"
            v-model="produto"
            :options="optionsProdutos"
          >
          </q-select>
        </div>
      </div>
    </div>
    <grafico-curva-repasse></grafico-curva-repasse>
    <cards-controladora></cards-controladora>
  </q-page>
</template>

<script>
import CardsControladora from "src/components/CardsControladora.vue";
import { defineComponent, ref } from "vue";
import GraficoCurvaRepasse from "../components/GraficoCurvaRepasse.vue";
// import ECharts.js modules manually to reduce bundle size

export default defineComponent({
  name: "IndexPage",
  setup() {
    return {
      optionsControladoras: ["Tenda", "MRV"],
      optionsProdutos: ["Apoio a produção", "PEC", "Outros"],
      controladora: ref(),
      produto: ref(),
    };
  },
  components: { GraficoCurvaRepasse, CardsControladora },
});
</script>
