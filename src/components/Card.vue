<template>
  <div class="card">
    <div class="card-top">
      <div class="section-left">
        <maininfo></maininfo>
        <tags></tags>
      </div>
      <div class="section-right">
        <analytics v-bind:data="data"></analytics>
        <associated></associated>
      </div>
    </div>
    <div class="card-bottom">
      <p class="bottom-title">Активность на платформе</p>
      <div class="activity">
        <b-icon icon="star-fill"></b-icon>
        <p class="activity-title">Основатель</p>
        <b-icon icon="people-fill"></b-icon>
        <p class="activity-title">Участник</p>
      </div>
    </div>
    <div class="showcase">
        <projects/>
        <organisations/>
    </div>
  </div>
</template>

<script>
import maininfo from './Maininfo.vue'
import tags from './Tags.vue'
import analytics from './Analytics.vue'
import associated from './Associated.vue'
import projects from './Projects.vue'
import organisations from './Organisations.vue'

export default {
  name: 'Card',
  props: {
    data: {
      type: Object,
    }
  },
  components: {
    'maininfo': maininfo,
    'tags': tags,
    'analytics': analytics,
    'associated': associated,
    'projects': projects,
    'organisations': organisations,
  },
}
</script>

<style scoped>
.card {
  display: flex;
  margin-top: 30px;
  border: 0;
  border-radius: 24px;
  width: 75%;
}

.card-top {
  display: flex;
  flex-direction: row;
}

.section-left, .section-right {
  padding-top: 32px;
  display: flex;
  flex-direction: column;
}

.section-right {
  margin-right: 52px;
}

.card-bottom {
  margin-top: 46px;
  padding-left: 33px;
  border-bottom: 1px solid #E2E2E7;
}

.bottom-title {
  font-size: 16px;
  font-weight: 600;
}

.activity {
  margin-top: 18px;
  display: flex;
  flex-direction: row;
  align-items: center;
  font-weight: 600;
  margin-bottom: 13px;
}

p {
  margin: 0; padding: 0;
}

.activity-title {
  margin-left: 13px;
  margin-right: 36px;
}

.showcase {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  padding-left: 34px;
  padding-right: 34px;
}
</style>
