<template>
  <div class="projects-wrapper">
    <p class="projects-title">Проекты</p>
    <div class="projects-card">
      <div class="project-position">
        <b-icon icon="star-fill"></b-icon>
        <p class="activity-title">Основатель</p>
      </div>
      <div class="project-content-wrapper">
        <img class="project-avatar" src="../assets/project.svg">
        <div class="project-content">
          <p class="project-name">Орион</p>
          <p class="project-stage-title">Стадия проекта</p>
          <p class="project-stage">Создание прототипа</p>
          <p class="project-funding-title">Объем финансирования</p>
          <div class="project-funding">5-6 млн<b-icon class="triangle-icon" icon="triangle-fill"></b-icon><p class="funding-float">15%</p></div>
          <p class="project-description">Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore ...</p>
          <p class="project-moreinfo">Подробнее</p>
        </div>
        <div class="project-menu">
          <b-icon class="menuicon" icon="bookmark"></b-icon>
          <b-icon class="menuicon" icon="share"></b-icon>
          <b-icon class="menuicon" icon="chat-left-text"></b-icon>
          <b-icon class="menuicon" icon="slash-circle"></b-icon>
        </div>
      </div>
      <div class="project-tags">
        <b-button class="pillbutton" pill variant="outline-secondary">
          <svg id="button" width="16" height="16">
            <circle cx="8" cy="8" r="4" fill="#F6D616"/>
          </svg>
          Социальные услуги
        </b-button>
        <b-button class="pillbutton" pill variant="outline-secondary">
          <svg id="button" width="16" height="16">
            <circle cx="8" cy="8" r="4" fill="#F6D616"/>
          </svg>
          FoodTech
        </b-button>
        <b-button class="pillbutton" pill variant="outline-secondary">
          <svg id="button" width="16" height="16">
            <circle cx="8" cy="8" r="4" fill="#F6D616"/>
          </svg>
          Роботизация
        </b-button>
        <b-button class="pillbutton" pill variant="outline-secondary">
          <svg id="button" width="16" height="16">
            <circle cx="8" cy="8" r="4" fill="#ED5338"/>
          </svg>
          Роботизация
        </b-button>
        <b-button class="pillbutton" pill variant="outline-secondary">
          <svg id="button" width="16" height="16">
            <circle cx="8" cy="8" r="4" fill="#ED5338"/>
          </svg>
          FoodTech
        </b-button>
      </div>
    </div>
    <div class="project-nav">
      <b-icon class="button-chevron" icon="chevron-left"></b-icon>
      <svg id="annotation" width="48" height="16">
        <circle cx="8" cy="8" r="4" fill="#BDBDC7"/>
        <circle cx="24" cy="8" r="4" fill="#4E8EF8"/>
        <circle cx="40" cy="8" r="4" fill="#BDBDC7"/>
      </svg>
      <b-icon class="button-chevron" icon="chevron-right"></b-icon>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Navbar',
}
</script>

<style scoped>
p {
  margin:0;padding:0;
}

.projects-wrapper {
  margin-right: 6px;
  width: auto;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.projects-title {
  font-size: 14px;
  font-weight: 600;
  margin-top: 18px;
  margin-bottom: 18px;
  align-self: flex-start;
}

.project-position {
  display: flex;
  flex-direction: row;
  align-items: center;
  margin-bottom: 9px;
}

.projects-card {
  display: flex;
  flex-direction: column;
  padding: 19px;
  padding-top: 9px;
  box-shadow: 0px 0px 15px rgba(0, 0, 0, 0.1);
  border-radius: 7px;
}

.activity-title {
  margin-left: 13px;
}

.project-content-wrapper {
  display: flex;
  flex-direction: row;
  align-items: flex-start;
}

.project-content {
  display: flex;
  flex-direction: column;
}

.project-avatar {
  margin-right: 30px;
}

.project-name {
  font-size: 16px;
  font-weight: 600;
  margin-bottom: 14px;
  line-height: 19px;
}

.project-stage-title {
  color: #777F90;
  line-height: 15px;
  margin-bottom: 6px;
}

.project-stage {
  font-size: 16px;
  font-weight: 600;
  line-height: 15px;
  margin-bottom: 10px;
}

.project-funding-title {
  color: #777F90;
  line-height: 15px;
  margin-bottom: 6px;
}

.project-funding {
  font-size: 16px;
  font-weight: 600;
  line-height: 15px;
  display: flex;
  flex-direction: row;
  margin-bottom: 16px;
}

.triangle-icon {
  margin-left: 24px;
  color: #00B929;
}

.funding-float {
  margin-left: 8px;
  color: #00B9A9;
  font-size: 14px;
  font-weight: 600;
}

.project-description {
  color: #777F90;
}

.project-moreinfo {
  color: #4E8EF8;
  text-decoration:underline;
  font-weight: 600;
  margin-top: 8px;
  margin-bottom: 24px;
}

.project-menu {
  display: flex;
  flex-direction: column;
  margin-left: 12px;
}

.menuicon {
  margin-bottom: 14px;
  color: #BDBDC7;
  width: 18px;
  height: 18px;
  opacity: 0.7;
  transition: 0.5s;
}

.menuicon:hover {
  opacity: 1;
  transition: 0.5s;
  cursor: pointer;
}

.pillbutton {
  margin-right: 15px;
  margin-bottom: 10px;
}

.project-nav {
  margin-top: 16px;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  margin-bottom: 26px;
}

.project-nav circle {
  cursor: pointer;
}

.button-chevron {
  color: #4E8EF8;
  width: 20px;
  height: 20px;
  cursor: pointer;
}

</style>
