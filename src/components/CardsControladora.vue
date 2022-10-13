<template>
  <div>
    <section class="info-tiles py-2">
      <div class="tile is-ancestor has-text-centered">
        <div class="tile is-parent">
          <article
            class="tile is-child notification is-primary card l-bg-cherry"
          >
            <div class="card-statistic-3">
              <div class="card-icon card-icon-large">
                <i class="fas fa-building"></i>
              </div>
              <p class="is-size-5 heading-card">Prazo Médio de Obras</p>
              <p class="title title-card">{{ PZ_OBRA_AVG }}</p>
              <p class="is-size-7 subtitle-card">
                Prazo Médio de Obras
                <!-- <span>{{ controladora.value }}</span> -->
              </p>
              <div class="progress mt-1" data-height="8" style="height: 8px">
                <!--                <div
                  class="progress-bar l-bg-cyan"
                  role="progressbar"
                  data-width="25%"
                  aria-valuenow="25"
                  aria-valuemin="0"
                  aria-valuemax="100"
                  style="width: 25%"
                ></div>-->
              </div>
            </div>
          </article>
        </div>
        <div class="tile is-parent">
          <article class="tile is-child notification card l-bg-blue-dark">
            <div class="card-statistic-3">
              <div class="card-icon card-icon-large">
                <i class="fas fa-solid fa-person-digging"></i>
              </div>
              <p class="is-size-5 heading-card">Percentual de Obra Executada</p>
              <p class="title title-card">{{ PC_OBRA_EXECUTADA_FORMATADO }}%</p>
              <p class="is-size-7 subtitle-card">Média de Execução</p>
              <div class="progress mt-1" data-height="8" style="height: 8px">
                <!--                <div
                  class="progress-bar l-bg-cyan"
                  role="progressbar"
                  data-width="25%"
                  aria-valuenow="25"
                  aria-valuemin="0"
                  aria-valuemax="100"
                  style="width: 25%"
                ></div>-->
              </div>
            </div>
          </article>
        </div>
        <div class="tile is-parent">
          <article class="tile is-child notification card l-bg-green-dark">
            <!--<p class="is-size-5 heading-card">Saldo Amortizado EPR</p>
            <p class="title title-card">R$4.339.000,00</p>
            <p class="is-size-7 subtitle-card">
              Contrato Pai no SIACI Construção
            </p>-->
            <div class="card-statistic-3">
              <div class="card-icon card-icon-large">
                <i class="fas fa-dollar-sign"></i>
              </div>
              <p class="is-size-5 heading-card">Total Orçamento Compra/Venda</p>
              <p class="title title-card">
                {{ VR_ORCAMENTO_COMPRA_VENDA_SUM_FORMATADO }}
              </p>
              <p class="is-size-7 subtitle-card">
                Soma Total do valor de Compra/venda
              </p>
              <div class="progress mt-1" data-height="8" style="height: 8px">
                <!--                <div
                  class="progress-bar l-bg-cyan"
                  role="progressbar"
                  data-width="25%"
                  aria-valuenow="25"
                  aria-valuemin="0"
                  aria-valuemax="100"
                  style="width: 25%"
                ></div>-->
              </div>
            </div>
          </article>
        </div>
        <div class="tile is-parent">
          <article class="tile is-child notification card l-bg-orange-dark">
            <!--<p class="is-size-5 heading-card">Saldo Amortizado EPR</p>
            <p class="title title-card">R$4.339.000,00</p>
            <p class="is-size-7 subtitle-card">
              Contrato Pai no SIACI Construção
            </p>-->
            <div class="card-statistic-3">
              <div class="card-icon card-icon-large">
                <i class="fas fa-solid fa-sack-dollar"></i>
              </div>
              <p class="is-size-5 heading-card">Valor Compra/Venda Unidade</p>
              <p class="title title-card">
                {{ VR_COMPRA_VENDA_UNIDADE_FORMATADO }}
              </p>
              <p class="is-size-7 subtitle-card">Valor Compra/Venda Unidade</p>
              <div class="progress mt-1" data-height="8" style="height: 8px">
                <!--                <div
                  class="progress-bar l-bg-cyan"
                  role="progressbar"
                  data-width="25%"
                  aria-valuenow="25"
                  aria-valuemin="0"
                  aria-valuemax="100"
                  style="width: 25%"
                ></div>-->
              </div>
            </div>
          </article>
        </div>
      </div>

      <div class="tile is-ancestor has-text-centered">
        <div class="tile is-parent">
          <article class="tile is-child notification card l-bg-cyan">
            <!--<p class="is-size-5 heading-card">Saldo Amortizado EPR</p>
            <p class="title title-card">R$4.339.000,00</p>
            <p class="is-size-7 subtitle-card">
              Contrato Pai no SIACI Construção
            </p>-->
            <div class="card-statistic-3">
              <div class="card-icon card-icon-large">
                <i class="fas fa-solid fa-wallet"></i>
              </div>
              <p class="is-size-5 heading-card">Total Saldo Mutuário PF</p>
              <p class="title title-card">
                {{ VR_SALDO_MUTUARIO_PESSOA_FISICA_SUM_FORMATADO }}
              </p>
              <p class="is-size-7 subtitle-card">
                Soma Saldo Mutuário Pessoa Física
              </p>
              <div class="progress mt-1" data-height="8" style="height: 8px">
                <!--                <div
                  class="progress-bar l-bg-cyan"
                  role="progressbar"
                  data-width="25%"
                  aria-valuenow="25"
                  aria-valuemin="0"
                  aria-valuemax="100"
                  style="width: 25%"
                ></div>-->
              </div>
            </div>
          </article>
        </div>
        <div class="tile is-parent">
          <article class="tile is-child notification card l-bg-green">
            <!--<p class="is-size-5 heading-card">Saldo Amortizado EPR</p>
            <p class="title title-card">R$4.339.000,00</p>
            <p class="is-size-7 subtitle-card">
              Contrato Pai no SIACI Construção
            </p>-->
            <div class="card-statistic-3">
              <div class="card-icon card-icon-large">
                <i class="fas fa-solid fa-hand-holding-dollar"></i>
              </div>
              <p class="is-size-5 heading-card">Total Saldo Mutuário PJ</p>
              <p class="title title-card">
                {{ VR_SALDO_MUTUARIO_PESSOA_JURIDICA_SUM_FORMATADO }}
              </p>
              <p class="is-size-7 subtitle-card">
                Soma Saldo Mutuário Pessoa Jurídica
              </p>
              <div class="progress mt-1" data-height="8" style="height: 8px">
                <!--                <div
                  class="progress-bar l-bg-cyan"
                  role="progressbar"
                  data-width="25%"
                  aria-valuenow="25"
                  aria-valuemin="0"
                  aria-valuemax="100"
                  style="width: 25%"
                ></div>-->
              </div>
            </div>
          </article>
        </div>
        <div class="tile is-parent">
          <article class="tile is-child notification card l-bg-cherry">
            <!--<p class="is-size-5 heading-card">Saldo Amortizado EPR</p>
            <p class="title title-card">R$4.339.000,00</p>
            <p class="is-size-7 subtitle-card">
              Contrato Pai no SIACI Construção
            </p>-->
            <div class="card-statistic-3">
              <div class="card-icon card-icon-large">
                <i class="fas fa-solid fa-money-check-dollar"></i>
              </div>
              <p class="is-size-5 heading-card">Total Saldo Devedor PJ</p>
              <p class="title title-card">
                {{ VR_SALDO_DEVEDOR_PESSOA_JURIDICA_SUM_FORMATADO }}
              </p>
              <p class="is-size-7 subtitle-card">
                Soma Saldo Devedor Pessoa Jurídica
              </p>
              <div class="progress mt-1" data-height="8" style="height: 8px">
                <!--                <div
                  class="progress-bar l-bg-cyan"
                  role="progressbar"
                  data-width="25%"
                  aria-valuenow="25"
                  aria-valuemin="0"
                  aria-valuemax="100"
                  style="width: 25%"
                ></div>-->
              </div>
            </div>
          </article>
        </div>
        <div class="tile is-parent">
          <article class="tile is-child notification card l-bg-green">
            <!--<p class="is-size-5 heading-card">Saldo Amortizado EPR</p>
            <p class="title title-card">R$4.339.000,00</p>
            <p class="is-size-7 subtitle-card">
              Contrato Pai no SIACI Construção
            </p>-->
            <div class="card-statistic-3">
              <div class="card-icon card-icon-large">
                <i class="fas fa-solid fa-coins"></i>
              </div>
              <p class="is-size-5 heading-card">Valor Total de Financiamento</p>
              <p class="title title-card">
                {{ VR_TOTAL_FINANCIAMENTO_SUM_FORMATADO }}
              </p>
              <p class="is-size-7 subtitle-card">Soma Total Financiamento</p>
              <div class="progress mt-1" data-height="8" style="height: 8px">
                <!--                <div
                  class="progress-bar l-bg-cyan"
                  role="progressbar"
                  data-width="25%"
                  aria-valuenow="25"
                  aria-valuemin="0"
                  aria-valuemax="100"
                  style="width: 25%"
                ></div>-->
              </div>
            </div>
          </article>
        </div>
      </div>
      <div class="tile is-ancestor has-text-centered">
        <div class="tile is-parent">
          <article class="tile is-child notification card l-bg-cyan">
            <!--<p class="is-size-5 heading-card">Saldo Amortizado EPR</p>
            <p class="title title-card">R$4.339.000,00</p>
            <p class="is-size-7 subtitle-card">
              Contrato Pai no SIACI Construção
            </p>-->
            <div class="card-statistic-3">
              <div class="card-icon card-icon-large">
                <i class="fas fa-solid fa-file-invoice-dollar"></i>
              </div>
              <p class="is-size-5 heading-card">Valor Total FGTS</p>
              <p class="title title-card">
                {{ VR_TOTAL_FGTS_SUM_FORMATADO }}
              </p>
              <p class="is-size-7 subtitle-card">Soma Total FGTS</p>
              <div class="progress mt-1" data-height="8" style="height: 8px">
                <!--                <div
                  class="progress-bar l-bg-cyan"
                  role="progressbar"
                  data-width="25%"
                  aria-valuenow="25"
                  aria-valuemin="0"
                  aria-valuemax="100"
                  style="width: 25%"
                ></div>-->
              </div>
            </div>
          </article>
        </div>
        <div class="tile is-parent">
          <article class="tile is-child notification card l-bg-orange">
            <!--<p class="is-size-5 heading-card">Saldo Amortizado EPR</p>
            <p class="title title-card">R$4.339.000,00</p>
            <p class="is-size-7 subtitle-card">
              Contrato Pai no SIACI Construção
            </p>-->
            <div class="card-statistic-3">
              <div class="card-icon card-icon-large">
                <i class="fas fa-solid fa-circle-dollar-to-slot"></i>
              </div>
              <p class="is-size-5 heading-card">
                Total Financiamento Pessoa Jurídica
              </p>
              <p class="title title-card">
                {{ VR_FINANCIAMENTO_PESSOA_JURIDICA_SUM_FORMATADO }}
              </p>
              <p class="is-size-7 subtitle-card">
                Soma Total Financiamento Pessoa Jurídica
              </p>
              <div class="progress mt-1" data-height="8" style="height: 8px">
                <!--                <div
                  class="progress-bar l-bg-cyan"
                  role="progressbar"
                  data-width="25%"
                  aria-valuenow="25"
                  aria-valuemin="0"
                  aria-valuemax="100"
                  style="width: 25%"
                ></div>-->
              </div>
            </div>
          </article>
        </div>
        <div class="tile is-parent">
          <article class="tile is-child notification card l-bg-green">
            <!--<p class="is-size-5 heading-card">Saldo Amortizado EPR</p>
            <p class="title title-card">R$4.339.000,00</p>
            <p class="is-size-7 subtitle-card">
              Contrato Pai no SIACI Construção
            </p>-->
            <div class="card-statistic-3">
              <div class="card-icon card-icon-large">
                <i class="fas fa-solid fa-money-bill-wave"></i>
              </div>
              <p class="is-size-5 heading-card">Financiamento Pessoa Física</p>
              <p class="title title-card">
                {{ PRC_FINANCIAMENTO_PESSOA_FISICA_AVG_FORMATADO }}%
              </p>
              <p class="is-size-7 subtitle-card">
                Percentual Financiamento Pessoa Física
              </p>
              <div class="progress mt-1" data-height="8" style="height: 8px">
                <!--                <div
                  class="progress-bar l-bg-cyan"
                  role="progressbar"
                  data-width="25%"
                  aria-valuenow="25"
                  aria-valuemin="0"
                  aria-valuemax="100"
                  style="width: 25%"
                ></div>-->
              </div>
            </div>
          </article>
        </div>
        <div class="tile is-parent">
          <article class="tile is-child notification card l-bg-blue-dark">
            <!--<p class="is-size-5 heading-card">Saldo Amortizado EPR</p>
            <p class="title title-card">R$4.339.000,00</p>
            <p class="is-size-7 subtitle-card">
              Contrato Pai no SIACI Construção
            </p>-->
            <div class="card-statistic-3">
              <div class="card-icon card-icon-large">
                <i class="fas fa-solid fa-money-bills"></i>
              </div>
              <p class="is-size-5 heading-card">
                Financiamento Pessoa Jurídica
              </p>
              <p class="title title-card">
                {{ PRC_FINANCIAMENTO_PESSOA_JURIDICA_AVG_FORMATADO }}%
              </p>
              <p class="is-size-7 subtitle-card">
                Percentual Financiamento Pessoa Jurídica
              </p>
              <div class="progress mt-1" data-height="8" style="height: 8px">
                <!--                <div
                  class="progress-bar l-bg-cyan"
                  role="progressbar"
                  data-width="25%"
                  aria-valuenow="25"
                  aria-valuemin="0"
                  aria-valuemax="100"
                  style="width: 25%"
                ></div>-->
              </div>
            </div>
          </article>
        </div>
      </div>
    </section>
  </div>
</template>
<script>
import { number } from "echarts";
import { defineComponent, ref } from "vue";

const formatter = new Intl.NumberFormat("pt-BR", {
  style: "currency",
  currency: "BRL",
});

export default defineComponent({
  props: {
    controladora: null,
  },
  setup() {
    return {
      PZ_OBRA_AVG: ref(),
      PC_OBRA_EXECUTADA: ref(0),
      VR_ORCAMENTO_COMPRA_VENDA_SUM: ref(),
      VR_COMPRA_VENDA_UNIDADE: ref(),
      VR_SALDO_MUTUARIO_PESSOA_FISICA_SUM: ref(),
      VR_SALDO_MUTUARIO_PESSOA_JURIDICA_SUM: ref(),
      VR_SALDO_DEVEDOR_PESSOA_JURIDICA_SUM: ref(),
      VR_TOTAL_FINANCIAMENTO_SUM: ref(),
      VR_TOTAL_FGTS_SUM: ref(),
      VR_FINANCIAMENTO_PESSOA_JURIDICA_SUM: ref(),
      PRC_FINANCIAMENTO_PESSOA_JURIDICA_AVG: ref(),
      PRC_FINANCIAMENTO_PESSOA_FISICA_AVG: ref(),
    };
  },
  watch: {
    controladora: function (newVal) {
      this.fetchData(newVal);
    },
  },
  methods: {
    async fetchData(cnpj) {
      let resp = await fetch(
        "/indices-operacionais/backend/get_controladora.php?CNPJ=" +
          cnpj.value +
          "&OPCAO=card"
      );
      let data = await resp.json();

      this.PZ_OBRA_AVG = data[0].PZ_OBRA_AVG;
      this.PC_OBRA_EXECUTADA = data[0].PC_OBRA_EXECUTADA;
      this.VR_ORCAMENTO_COMPRA_VENDA_SUM =
        data[0].VR_ORCAMENTO_COMPRA_VENDA_SUM;
      this.VR_COMPRA_VENDA_UNIDADE = data[0].VR_COMPRA_VENDA_UNIDADE;
      this.VR_SALDO_MUTUARIO_PESSOA_FISICA_SUM =
        data[0].VR_SALDO_MUTUARIO_PESSOA_FISICA_SUM;
      this.VR_SALDO_MUTUARIO_PESSOA_JURIDICA_SUM =
        data[0].VR_SALDO_MUTUARIO_PESSOA_JURIDICA_SUM;
      this.VR_SALDO_DEVEDOR_PESSOA_JURIDICA_SUM =
        data[0].VR_SALDO_DEVEDOR_PESSOA_JURIDICA_SUM;
      this.VR_TOTAL_FINANCIAMENTO_SUM = data[0].VR_TOTAL_FINANCIAMENTO_SUM;
      this.VR_TOTAL_FGTS_SUM = data[0].VR_TOTAL_FGTS_SUM;
      this.VR_FINANCIAMENTO_PESSOA_JURIDICA_SUM =
        data[0].VR_FINANCIAMENTO_PESSOA_JURIDICA_SUM;
      this.PRC_FINANCIAMENTO_PESSOA_JURIDICA_AVG =
        data[0].PRC_FINANCIAMENTO_PESSOA_JURIDICA_AVG;
      this.PRC_FINANCIAMENTO_PESSOA_FISICA_AVG =
        data[0].PRC_FINANCIAMENTO_PESSOA_FISICA_AVG;
    },
  },
  computed: {
    VR_ORCAMENTO_COMPRA_VENDA_SUM_FORMATADO() {
      return formatter.format(this.VR_ORCAMENTO_COMPRA_VENDA_SUM);
    },
    PC_OBRA_EXECUTADA_FORMATADO() {
      return parseFloat(this.PC_OBRA_EXECUTADA * 100).toFixed(2);
    },
    VR_COMPRA_VENDA_UNIDADE_FORMATADO() {
      return formatter.format(this.VR_COMPRA_VENDA_UNIDADE);
    },
    VR_SALDO_MUTUARIO_PESSOA_FISICA_SUM_FORMATADO() {
      return formatter.format(this.VR_SALDO_MUTUARIO_PESSOA_FISICA_SUM);
    },
    VR_SALDO_MUTUARIO_PESSOA_JURIDICA_SUM_FORMATADO() {
      return formatter.format(this.VR_SALDO_MUTUARIO_PESSOA_JURIDICA_SUM);
    },
    VR_SALDO_DEVEDOR_PESSOA_JURIDICA_SUM_FORMATADO() {
      return formatter.format(this.VR_SALDO_DEVEDOR_PESSOA_JURIDICA_SUM);
    },
    VR_TOTAL_FINANCIAMENTO_SUM_FORMATADO() {
      return formatter.format(this.VR_TOTAL_FINANCIAMENTO_SUM);
    },
    VR_TOTAL_FGTS_SUM_FORMATADO() {
      return formatter.format(this.VR_TOTAL_FGTS_SUM);
    },
    VR_FINANCIAMENTO_PESSOA_JURIDICA_SUM_FORMATADO() {
      return formatter.format(this.VR_FINANCIAMENTO_PESSOA_JURIDICA_SUM);
    },
    PRC_FINANCIAMENTO_PESSOA_JURIDICA_AVG_FORMATADO() {
      return parseFloat(
        this.PRC_FINANCIAMENTO_PESSOA_JURIDICA_AVG * 100
      ).toFixed(2);
    },
    PRC_FINANCIAMENTO_PESSOA_FISICA_AVG_FORMATADO() {
      return parseFloat(this.PRC_FINANCIAMENTO_PESSOA_FISICA_AVG * 100).toFixed(
        2
      );
    },
  },
});
</script>
<style scoped>
.card {
  background-color: #fff;
  border-radius: 10px;
  border: none;
  position: relative;
  margin-bottom: 30px;
  box-shadow: 0 0.46875rem 2.1875rem rgba(90, 97, 105, 0.1),
    0 0.9375rem 1.40625rem rgba(90, 97, 105, 0.1),
    0 0.25rem 0.53125rem rgba(90, 97, 105, 0.12),
    0 0.125rem 0.1875rem rgba(90, 97, 105, 0.1);
}
.l-bg-cherry {
  background: linear-gradient(to right, #493240, #f09) !important;
  color: #fff;
}
.l-bg-blue-dark {
  background: linear-gradient(to right, #373b44, #4286f4) !important;
  color: #fff;
}
.l-bg-green-dark {
  background: linear-gradient(to right, #0a504a, #38ef7d) !important;
  color: #fff;
}
.l-bg-orange-dark {
  background: linear-gradient(to right, #a86008, #ffba56) !important;
  color: #fff;
}
.card .card-statistic-3 .card-icon-large .fas {
  font-size: 100px;
}
.card .card-statistic-3 .card-icon {
  text-align: center;
  line-height: 50px;
  margin-left: -10px;
  color: #000;
  position: absolute;
  right: 15px;
  top: 20px;
  opacity: 0.1;
}
.l-bg-cyan {
  background: linear-gradient(to right, #373b44, #84c0ec 100%) !important;
  color: #fff;
}
.l-bg-green {
  background: linear-gradient(to right, #0a504a, #43e794 100%) !important;
  color: #fff;
}
.l-bg-orange {
  background: linear-gradient(to right, #f9900e, #ffba56) !important;
  color: #fff;
}
</style>
