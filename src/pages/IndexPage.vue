<template>
  <q-page padding>
    <div class="q-pa-md">
      <div class="columns">
        <div class="column is-3">
          <q-select
            v-model="controladora"
            :options="options"
            label="Controladoras"
            emit-label
          />
        </div>
        <!-- <q-badge color="secondary" multi-line>
          Model: "{{ controladora }}"
        </q-badge> -->
        <!--<div class="column is-2">
          <q-select
            label="Produto"
            v-model="produto"
            :options="optionsProdutos"
          >
          </q-select>
        </div>-->
      </div>
    </div>
    <grafico-curva-repasse :controladora="controladora"></grafico-curva-repasse>
    <cards-controladora :controladora="controladora"></cards-controladora>
    <grid-controladora :controladora="controladora"></grid-controladora>
  </q-page>
</template>

<script>
import { defineComponent, ref } from "vue";
import CardsControladora from "../components/CardsControladora.vue";
import GraficoCurvaRepasse from "../components/GraficoCurvaRepasse.vue";
import GridControladora from "../components/GridControladora.vue";

export default defineComponent({
  name: "IndexPage",
  methods: {
    changeControladora() {},
  },
  setup() {
    return {
      controladora: ref(0),
      options: [
        {
          label: "A YOSHII",
          value: "78016003000100",
        },
        {
          label: "ATUA",
          value: "8741800000175",
        },
        {
          label: "BENX BUENO NETTO",
          value: "8113807000142",
        },
        {
          label: "BILD",
          value: "8964236000150",
        },
        {
          label: "BRZ",
          value: "4065053000141",
        },
        {
          label: "CANOPUS",
          value: "97552976000109",
        },
        {
          label: "CARVALHO HOSKEN",
          value: "33342023000133",
        },
        {
          label: "CASAALTA",
          value: "77578623000170",
        },
        {
          label: "CCDI CAMARGO CORREA",
          value: "67203208000189",
        },
        { label: "CURY", value: "8797760000183" },
        {
          label: "CYRELA",
          value: "73178600000118",
        },
        {
          label: "DIRECIONAL",
          value: "16614075000100",
        },
        {
          label: "EBM CONSTRUTORA",
          value: "17211861000111",
        },
        {
          label: "ECON",
          value: "22104030000180",
        },
        {
          label: "EMCCAMP",
          value: "19403252000190",
        },
        {
          label: "EVEN",
          value: "43470988000165",
        },
        {
          label: "EZTEC",
          value: "8312229000173",
        },
        {
          label: "FIBRA EXPERTS",
          value: "6943044000131",
        },
        {
          label: "GAFISA",
          value: "1545826000107",
        },
        {
          label: "HM ENGENHARIA",
          value: "47062179000175",
        },
        {
          label: "INTER",
          value: "9611768000176",
        },
        {
          label: "JOAO FORTES",
          value: "33035536000100",
        },
        {
          label: "JOTANUNES",
          value: "16202491000193",
        },
        {
          label: "KALLAS",
          value: "9146451000106",
        },
        {
          label: "MELNICK EVEN",
          value: "12181987000177",
        },
        {
          label: "MOURA DUBEUX",
          value: "12049631000184",
        },
        {
          label: "MRV",
          value: "8343492000120",
        },
        {
          label: "ODEBRECHT OR",
          value: "10917143000116",
        },
        {
          label: "PACAEMBU",
          value: "96298013000168",
        },
        {
          label: "PATRIMAR",
          value: "23236821000127",
        },
        {
          label: "PDG",
          value: "2950811000189",
        },
        {
          label: "PLANO E PLANO",
          value: "24230275000180",
        },
        {
          label: "PRECON",
          value: "19223387000173",
        },
        {
          label: "QGDI QUEIROZ GALVAO",
          value: "11535028000140",
        },
        {
          label: "REALIZA",
          value: "16991176000192",
        },
        {
          label: "RIBEIRA",
          value: "7544616000172",
        },
        {
          label: "RODOBENS",
          value: "67010660000124",
        },
        {
          label: "ROSSI",
          value: "61065751000180",
        },
        {
          label: "SA CAVALCANTE",
          value: "8056195000101",
        },
        {
          label: "SAO JOSE",
          value: "7785320000143",
        },
        {
          label: "SETIN",
          value: "51194280000157",
        },
        {
          label: "TECNISA",
          value: "8065557000112",
        },
        {
          label: "TEGRA",
          value: "30213493000184",
        },
        {
          label: "TENDA",
          value: "71476527000135",
        },
        {
          label: "TRISUL",
          value: "8811643000127",
        },
        {
          label: "VITACON",
          value: "11144772000113",
        },
        {
          label: "YOU INC",
          value: "11284204000118",
        },
      ],
      optionsProdutos: ["Apoio a produção", "PEC", "Outros"],
      produto: ref(),
    };
  },
  components: { GraficoCurvaRepasse, CardsControladora, GridControladora },
});
</script>
