<template>
  <div class="analytics">
    <p class="analytics-title">Аналитика профиля</p>
    <div class="analytics-data">
      <div class="analytics-mentions">
        <p class="mentions-title">
          Число упоминаний
        </p>
        <p class="mentions-amount">
          74
        </p>
        <p class="mentions-signature">
          Подпись текст
        </p>
      </div>
      <div class="analytics-replies">
        <p class="replies-title">
          Отвечает на запросы
        </p>
        <p class="replies-amount">
          87%
        </p>
        <p class="replies-signature">
          Санкт-Петербург, Россия
        </p>
      </div>
    </div>
    <graph v-bind:data="data"/>
  </div>
</template>

<script>
import graph from './Graph.vue'

export default {
  name: 'Analytics',
  props: {
    data: {
      type: Object,
    }
  },
  components: {
    'graph': graph,
  },
}
</script>

<style scoped>
  .analytics {
    display: flex;
    flex-direction: column;
  }

  .analytics-title {
    font-size: 16px;
    font-weight: 600;
    margin-left: 8px;
  }

  .analytics-data {
    display: flex;
    flex-direction: row;
  }

  .analytics-mentions, .analytics-replies {
    display: flex;
    flex-direction: column;
    align-items: center;
    box-shadow: 0px 0px 15px rgba(0, 0, 0, 0.1);
    border-radius: 7px;
    margin: 8px;
    width: 181px;
    height: 182px;
  }

  .mentions-title, .replies-title {
    margin-top: 16px;
    font-weight: 600;
  }

  .mentions-amount, .replies-amount {
    font-size: 72px;
    line-height: 88px;
  }

  .mentions-signature, .replies-signature {
    color: #777F90;
  }
</style>
