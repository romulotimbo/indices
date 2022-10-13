<template>
  <div>
    <q-table
      dense
      :rows="rows"
      :columns="columns"
      row-key="NU_CONTRATO_EMPREENDIMENTO"
      title="Empreendimentos"
      :rows-per-page-options="[20, 40, 60, 80, 100]"
      :visible-columns="visibleColumns"
      :key="tableKey"
    >
      <template v-slot:top="props">
        <div class="col-2 q-table__title">Empreendimentos</div>

        <q-space />

        <div v-if="$q.screen.gt.xs" class="col">
          <q-toggle
            v-model="visibleColumns"
            val="NO_CONSTRUTORA"
            label="Construtora"
          />
          <q-toggle
            v-model="visibleColumns"
            val="NU_CONTRATO_EMPREENDIMENTO"
            label="Nº Contrato Empreendimento"
          />
          <q-toggle
            v-model="visibleColumns"
            val="NU_CONTRATO"
            label="Nº Contrato"
          />
          <q-toggle
            v-model="visibleColumns"
            val="NU_TIPO_PEDIDO"
            label="Tipo Pedido"
          />
          <q-toggle
            v-model="visibleColumns"
            val="DT_ASSINATURA"
            label="Dt. Assinatura"
          />
          <q-toggle v-model="visibleColumns" val="NU_APF" label="APF" />
          <q-toggle
            v-model="visibleColumns"
            val="NO_EMPREENDIMENTO"
            label="Nome Empreendimento"
          />

          <q-toggle
            v-model="visibleColumns"
            val="DT_INICIO_OBRA"
            label="Dt. Início Obra"
          />
          <q-toggle
            v-model="visibleColumns"
            val="DT_TERMINO_OBRA_ATUAL"
            label="Dt. Término Obra"
          />
          <q-toggle v-model="visibleColumns" val="PZ_OBRA" label="Pz. Obra" />

          <q-toggle
            v-model="visibleColumns"
            val="PC_OBRA_EXECUTADA"
            label="Pct. Obra Executada"
          />
          <q-toggle
            v-model="visibleColumns"
            val="QT_UNIDADE"
            label="Qtd. Unidades"
          />
          <q-toggle
            v-model="visibleColumns"
            val="QT_UNIDADE_FINANCIADA"
            label="Qtd. Unidades Financiadas"
          />
          <q-toggle
            v-model="visibleColumns"
            val="QT_UNIDADE_COMERCIALIZADA"
            label="Qtd. Unidades Comercializadas"
          />
          <q-toggle
            v-model="visibleColumns"
            val="VR_CUSTO_OBRA"
            label="Vr. Custo Obra"
          />
          <q-toggle
            v-model="visibleColumns"
            val="VR_ORCAMENTO_COMPRA_VENDA"
            label="Vr. Orçamento Compra/Venda"
          />
          <q-toggle
            v-model="visibleColumns"
            val="VR_SALDO_MUTUARIO_PESSOA_FISICA"
            label="Vr. Saldo Mutuário PF"
          />

          <q-toggle
            v-model="visibleColumns"
            val="VR_SALDO_MUTUARIO_PESSOA_JURIDICA"
            label="Vr. Saldo Mutuário PJ"
          />
          <q-toggle
            v-model="visibleColumns"
            val="VR_SALDO_DEVEDOR_PESSOA_JURIDICA"
            label="Vr. Saldo Devedor PJ"
          />
          <q-toggle
            v-model="visibleColumns"
            val="VR_TOTAL_FINANCIAMENTO"
            label="Vr. Total Financiamento"
          />
          <q-toggle
            v-model="visibleColumns"
            val="VR_TOTAL_FGTS"
            label="Vr. Total FGTS"
          />
          <q-toggle
            v-model="visibleColumns"
            val="VR_FINANCIAMENTO_PESSOA_JURIDICA"
            label="Vr. Financiamento PJ"
          />
          <q-toggle
            v-model="visibleColumns"
            val="PRC_FINANCIAMENTO_PESSOA_JURIDICA"
            label="Pct. Financiamento PJ"
          />
          <q-toggle
            v-model="visibleColumns"
            val="PRC_FINANCIAMENTO_PESSOA_FISICA"
            label="Pct. Financiamento PF"
          />
        </div>
        <q-select
          v-else
          v-model="visibleColumns"
          multiple
          borderless
          dense
          options-dense
          :display-value="$q.lang.table.columns"
          emit-value
          map-options
          :options="columns"
          option-value="name"
          style="min-width: 150px"
        />

        <q-btn
          flat
          round
          dense
          :icon="props.inFullscreen ? 'fullscreen_exit' : 'fullscreen'"
          @click="props.toggleFullscreen"
          class="q-ml-md"
        />
      </template>
    </q-table>
  </div>
</template>
<script>
import { ref } from "vue";
import { exportFile, useQuasar } from "quasar";

const columns = [
  {
    name: "NO_CONSTRUTORA",
    align: "center",
    label: "Construtora",
    field: "NO_CONSTRUTORA",
    sortable: true,
  },
  {
    name: "NU_CONTRATO_EMPREENDIMENTO",
    align: "center",
    label: "Nº Contrato Empreendimento",
    field: "NU_CONTRATO_EMPREENDIMENTO",
    sortable: true,
  },
  {
    name: "NU_CONTRATO",
    align: "center",
    label: "Nº Contrato",
    field: "NU_CONTRATO",
    sortable: true,
  },
  {
    name: "NU_TIPO_PEDIDO",
    align: "center",
    label: "Tipo Pedido",
    field: "NU_TIPO_PEDIDO",
    sortable: true,
  },
  {
    name: "DT_ASSINATURA",
    align: "center",
    label: "Dt. Assinatura",
    field: "DT_ASSINATURA",
    sortable: true,
  },
  {
    name: "NU_APF",
    align: "center",
    label: "APF",
    field: "NU_APF",
    sortable: true,
  },
  {
    name: "NO_EMPREENDIMENTO",
    align: "center",
    label: "Nome Empreendimento",
    field: "NO_EMPREENDIMENTO",
    sortable: true,
  },
  {
    name: "DT_INICIO_OBRA",
    align: "center",
    label: "Dt. Início Obra",
    field: "DT_INICIO_OBRA",
    sortable: true,
  },
  {
    name: "DT_TERMINO_OBRA_ATUAL",
    align: "center",
    label: "Dt. Término Obra",
    field: "DT_TERMINO_OBRA_ATUAL",
    sortable: true,
  },
  {
    name: "PZ_OBRA",
    align: "center",
    label: "Pz. Obra",
    field: "PZ_OBRA",
    sortable: true,
  },
  {
    name: "PC_OBRA_EXECUTADA",
    align: "center",
    label: "Pct. Obra Executada",
    field: "PC_OBRA_EXECUTADA",
    sortable: true,
  },
  {
    name: "QT_UNIDADE",
    align: "center",
    label: "Qtd. Unidades",
    field: "QT_UNIDADE",
    sortable: true,
  },
  {
    name: "QT_UNIDADE_FINANCIADA",
    align: "center",
    label: "Qtd. Unidades Financiadas",
    field: "QT_UNIDADE_FINANCIADA",
    sortable: true,
  },
  {
    name: "QT_UNIDADE_COMERCIALIZADA",
    align: "center",
    label: "Qtd. Unidades Comercializadas",
    field: "QT_UNIDADE_COMERCIALIZADA",
    sortable: true,
  },
  {
    name: "VR_CUSTO_OBRA",
    align: "center",
    label: "Vlr Custo Obra",
    field: "VR_CUSTO_OBRA",
    sortable: true,
  },
  {
    name: "VR_ORCAMENTO_COMPRA_VENDA",
    align: "center",
    label: "Vlr. Orçamento Compra/Venda",
    field: "VR_ORCAMENTO_COMPRA_VENDA",
    sortable: true,
  },
  {
    name: "VR_COMPRA_VENDA_UNIDADE",
    align: "center",
    label: "Vlr. Compra/Venda Unidade",
    field: "VR_COMPRA_VENDA_UNIDADE",
    sortable: true,
  },
  {
    name: "VR_SALDO_MUTUARIO_PESSOA_FISICA",
    align: "center",
    label: "Vlr. Saldo Mutuário PF",
    field: "VR_SALDO_MUTUARIO_PESSOA_FISICA",
    sortable: true,
  },
  {
    name: "VR_SALDO_MUTUARIO_PESSOA_JURIDICA",
    align: "center",
    label: "Vlr. Saldo Mutuário PJ",
    field: "VR_SALDO_MUTUARIO_PESSOA_JURIDICA",
    sortable: true,
  },
  {
    name: "VR_SALDO_DEVEDOR_PESSOA_JURIDICA",
    align: "center",
    label: "Vlr. Saldo Devedor PJ",
    field: "VR_SALDO_DEVEDOR_PESSOA_JURIDICA",
    sortable: true,
  },
  {
    name: "VR_TOTAL_FINANCIAMENTO",
    align: "center",
    label: "Vlr. Total Financiamento",
    field: "VR_TOTAL_FINANCIAMENTO",
    sortable: true,
  },
  {
    name: "VR_TOTAL_FGTS",
    align: "center",
    label: "Vlr. Total FGTS",
    field: "VR_TOTAL_FGTS",
    sortable: true,
  },
  {
    name: "VR_FINANCIAMENTO_PESSOA_JURIDICA",
    align: "center",
    label: "Vlr. Financiamento PJ",
    field: "VR_FINANCIAMENTO_PESSOA_JURIDICA",
    sortable: true,
  },
  {
    name: "PRC_FINANCIAMENTO_PESSOA_JURIDICA",
    align: "center",
    label: "Pct. Financiamento PJ",
    field: "PRC_FINANCIAMENTO_PESSOA_JURIDICA",
    sortable: true,
  },
  {
    name: "PRC_FINANCIAMENTO_PESSOA_FISICA",
    align: "center",
    label: "Pct. Financiamento PF",
    field: "PRC_FINANCIAMENTO_PESSOA_FISICA",
    sortable: true,
  },
];
const rows = [];
export default {
  setup() {
    return {
      NO_CONSTRUTORA: ref(),
      NU_CONTRATO_EMPREENDIMENTO: ref(),
      NU_CONTRATO: ref(),
      NU_TIPO_PEDIDO: ref(),
      DT_ASSINATURA: ref(),
      NU_APF: ref(),
      NO_EMPREENDIMENTO: ref(),
      DT_INICIO_OBRA: ref(),
      DT_TERMINO_OBRA_ATUAL: ref(),
      PZ_OBRA: ref(),
      PC_OBRA_EXECUTADA: ref(),
      QT_UNIDADE: ref(),
      QT_UNIDADE_FINANCIADA: ref(),
      QT_UNIDADE_COMERCIALIZADA: ref(),
      VR_CUSTO_OBRA: ref(),
      VR_ORCAMENTO_COMPRA_VENDA: ref(),
      VR_COMPRA_VENDA_UNIDADE: ref(),
      VR_SALDO_MUTUARIO_PESSOA_FISICA: ref(),
      VR_SALDO_MUTUARIO_PESSOA_JURIDICA: ref(),
      VR_SALDO_DEVEDOR_PESSOA_JURIDICA: ref(),
      VR_TOTAL_FINANCIAMENTO: ref(),
      VR_TOTAL_FGTS: ref(),
      VR_FINANCIAMENTO_PESSOA_JURIDICA: ref(),
      PRC_FINANCIAMENTO_PESSOA_JURIDICA: ref(),
      PRC_FINANCIAMENTO_PESSOA_FISICA: ref(),
      columns,
      rows,
      tableKey: 0,
      visibleColumns: ref([
        "NO_CONSTRUTORA",
        "NU_CONTRATO_EMPREENDIMENTO",
        "NU_CONTRATO",
        "NU_TIPO_PEDIDO",
        "DT_ASSINATURA",
        "NU_APF",
        "NO_EMPREENDIMENTO",
        "DT_INICIO_OBRA",
        "DT_TERMINO_OBRA_ATUAL",
        "PZ_OBRA",
        "PC_OBRA_EXECUTADA",
        "QT_UNIDADE",
        "QT_UNIDADE_FINANCIADA",
        "QT_UNIDADE_COMERCIALIZADA",
        "VR_CUSTO_OBRA",
        "VR_ORCAMENTO_COMPRA_VENDA",
        "VR_COMPRA_VENDA_UNIDADE",
        "VR_SALDO_MUTUARIO_PESSOA_FISICA",
        "VR_SALDO_MUTUARIO_PESSOA_JURIDICA",
        "VR_SALDO_DEVEDOR_PESSOA_JURIDICA",
        "VR_TOTAL_FINANCIAMENTO",
        "VR_TOTAL_FGTS",
        "VR_FINANCIAMENTO_PESSOA_JURIDICA",
        "PRC_FINANCIAMENTO_PESSOA_JURIDICA",
        "PRC_FINANCIAMENTO_PESSOA_FISICA",
      ]),
    };
  },
  props: {
    controladora: null,
  },
  watch: {
    controladora: function (newVal) {
      this.fetchData(newVal);
      this.tableKey = 0;
    },
  },
  async created() {
    console.log(this.visibleColumns);
  },

  methods: {
    async fetchData(cnpj) {
      let resp = await fetch(
        "/indices-operacionais/backend/get_controladora.php?CNPJ=" +
          cnpj.value +
          "&OPCAO=grid"
      );
      let data = await resp.json();

      this.rows = data;
      this.tableKey = 1;
      console.log("tableKey atualizou: ", this.tableKey);

      setTimeout(() => {
        this.visibleColumns = [];
        this.visibleColumns = [
          "NO_CONSTRUTORA",
          "NU_CONTRATO_EMPREENDIMENTO",
          "NU_CONTRATO",
          "NU_TIPO_PEDIDO",
          "DT_ASSINATURA",
          "NU_APF",
          "NO_EMPREENDIMENTO",
          "DT_INICIO_OBRA",
          "DT_TERMINO_OBRA_ATUAL",
          "PZ_OBRA",
          "PC_OBRA_EXECUTADA",
          "QT_UNIDADE",
          "QT_UNIDADE_FINANCIADA",
          "QT_UNIDADE_COMERCIALIZADA",
          "VR_CUSTO_OBRA",
          "VR_ORCAMENTO_COMPRA_VENDA",
          "VR_COMPRA_VENDA_UNIDADE",
          "VR_SALDO_MUTUARIO_PESSOA_FISICA",
          "VR_SALDO_MUTUARIO_PESSOA_JURIDICA",
          "VR_SALDO_DEVEDOR_PESSOA_JURIDICA",
          "VR_TOTAL_FINANCIAMENTO",
          "VR_TOTAL_FGTS",
          "VR_FINANCIAMENTO_PESSOA_JURIDICA",
          "PRC_FINANCIAMENTO_PESSOA_JURIDICA",
          "PRC_FINANCIAMENTO_PESSOA_FISICA",
        ];
      }, 1000);
    },
  },
};
</script>
<style scoped></style>
