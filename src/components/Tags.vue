<template>
  <div class="tags">
    <div class="needs-wrapper">
      <p class="needs-title">Потребности</p>
      <div class="needs">
        <b-button class="pillbutton" pill variant="outline-secondary">
          <svg id="annotation" width="16" height="16">
            <circle cx="8" cy="8" r="4" fill="#F6D616"/>
          </svg>
          Карьерная консультация
        </b-button>
        <b-button class="pillbutton" pill variant="outline-secondary">
          <svg id="button" width="16" height="16">
            <circle cx="8" cy="8" r="4" fill="#F6D616"/>
          </svg>
          Коучинг
        </b-button>
      </div>
    </div>
    <div class="branch-wrapper">
      <p class="branch-title">Отрасль/сфера деятельности</p>
      <div class="branch">
        <b-button class="pillbutton" pill variant="outline-secondary">
          <svg id="button" width="16" height="16">
            <circle cx="8" cy="8" r="4" fill="#ED5338"/>
          </svg>
          Роботизация
        </b-button>
      </div>
    </div>
    <div class="results-wrapper">
      <p class="results-title">Результаты</p>
      <b-button class="results-button" variant="primary">Лаборатория профиля<b-icon style="margin-left: 8px; margin-top: 4px;" icon="arrow-right"></b-icon></b-button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Tags',
}
</script>

<style scoped>
.tags {
    padding-left: 33px;
}

.needs-wrapper, .branch-wrapper, .results-wrapper {
  display: flex;
  flex-direction: column;
  margin-top: 28px;
}

.needs-wrapper {
  margin-top: 18px;
}

.needs-title, .branch-title, .results-title {
  font-size: 16px;
  font-weight: 600;
}

.needs, .branch {
  display: flex;
  flex-direction: row;
}

.pillbutton {
  margin-right: 11px;
}

.results-button {
  background-color: #4E8EF8;
  border-color: #4E8EF8;
  width: 223px;
  height: 40px;
  border-radius: 6px;
  font-weight: 600;
}
</style>
