<template>
  <div>
    <section class="info-tiles py-2">
      <div class="tile is-ancestor has-text-centered">
        <div class="tile is-parent">
          <article class="tile is-child notification is-primary">
            <p class="is-size-5 heading-card">Saldo Devedor PJ TOTAL</p>
            <p class="title title-card">R$4.339.000,00</p>
            <p class="is-size-7 subtitle-card">Empreendimento em obra</p>
          </article>
        </div>
        <div class="tile is-parent">
          <article class="tile is-child notification is-link">
            <p class="is-size-5 heading-card">Saldo Credor PJ TOTAL</p>
            <p class="title title-card">R$4.339.000,00</p>
            <p class="is-size-7 subtitle-card">Empreendimento em obra</p>
          </article>
        </div>
        <div class="tile is-parent">
          <q-circular-progress
            show-value
            font-size="12px"
            :value="value"
            size="50px"
            :thickness="0.22"
            color="teal"
            track-color="grey-3"
            class="q-ma-md"
          >
            {{ value }}%
          </q-circular-progress>
        </div>
        <div class="tile is-parent">
          <article class="tile is-child notification is-success">
            <p class="is-size-5 heading-card">Saldo Amortizado EPR</p>
            <p class="title title-card">R$4.339.000,00</p>
            <p class="is-size-7 subtitle-card">
              Contrato Pai no SIACI Construção
            </p>
          </article>
        </div>
      </div>

      <div class="tile is-ancestor has-text-centered">
        <div class="tile is-parent">
          <article class="tile is-child notification is-danger">
            <p class="is-size-5 heading-card">Valor Médio Financiamento</p>
            <p class="title title-card">R$339.000,00</p>
            <p class="is-size-7 subtitle-card">
              Valor de Repasse / Valor Venda Avaliação
            </p>
          </article>
        </div>
        <div class="tile is-parent">
          <article class="tile is-child notification is-primary">
            <p class="is-size-5 heading-card">Prazo Médio de Obra</p>
            <p class="title title-card">99 Mêses</p>
            <p class="is-size-7 subtitle-card">
              Média de Todos Empreendimentos Ativos
            </p>
          </article>
        </div>
        <div class="tile is-parent">
          <article class="tile is-child notification is-success">
            <p class="is-size-5 heading-card">Total de Empreendimentos</p>
            <p class="title title-card">99</p>
            <p class="is-size-7 subtitle-card">
              Qtd de Empreendimentos em Obra
            </p>
          </article>
        </div>
        <div class="tile is-parent">
          <article class="tile is-child notification is-link">
            <p class="is-size-6 heading-card">
              Empreendimentos com Saldo Devedor
            </p>
            <p class="title title-card">R$4.339.000,00</p>
            <p class="is-size-7 subtitle-card">
              Empreendimentos em Obra Saldo Devedor > 0
            </p>
          </article>
        </div>
      </div>
    </section>
  </div>
</template>
<script>
import { defineComponent } from "vue";

export default defineComponent({
  setup() {
    return {
      value: 81,
    };
  },
});
</script>

<style scoped></style>
