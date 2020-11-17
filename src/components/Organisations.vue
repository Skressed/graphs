<template>
  <div class="orgs-wrapper">
    <p class="orgs-title">Проекты</p>
    <div class="orgs-card">
      <div class="orgs-position">
        <b-icon icon="star-fill"></b-icon>
        <p class="activity-title">Основатель</p>
      </div>
      <div class="orgs-content-wrapper">
        <div class="orgs-left">
          <img class="orgs-avatar" src="../assets/organisation.svg">
          <img class="orgs-tag" src="../assets/pro-user.svg">
        </div>
        <div class="orgs-content">
          <p class="orgs-name">Стройтех</p>
          <p class="orgs-description">Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore ...</p>
          <p class="orgs-moreinfo">Подробнее</p>
        </div>
        <div class="orgs-menu">
          <b-icon class="menuicon" icon="bookmark"></b-icon>
          <b-icon class="menuicon" icon="share"></b-icon>
          <b-icon class="menuicon" icon="chat-left-text"></b-icon>
          <b-icon class="menuicon" icon="slash-circle"></b-icon>
        </div>
      </div>
      <div class="orgs-tags">
        <b-button class="pillbutton" pill variant="outline-secondary">
          <svg id="button" width="16" height="16">
            <circle cx="8" cy="8" r="4" fill="#2EB349"/>
          </svg>
          Роботизация
        </b-button>
        <b-button class="pillbutton" pill variant="outline-secondary">
          <svg id="button" width="16" height="16">
            <circle cx="8" cy="8" r="4" fill="#2EB349"/>
          </svg>
          FoodTech
        </b-button>
        <b-button class="pillbutton" pill variant="outline-secondary">
          <svg id="button" width="16" height="16">
            <circle cx="8" cy="8" r="4" fill="#F6D616"/>
          </svg>
          Социальные услуги
        </b-button>
        <b-button class="pillbutton" pill variant="outline-secondary">
          <svg id="button" width="16" height="16">
            <circle cx="8" cy="8" r="4" fill="#ED5338"/>
          </svg>
          FoodTech
        </b-button>
      </div>
    </div>
    <div class="orgs-nav">
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

.orgs-wrapper {
  margin-left: 6px;
  width: auto;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.orgs-title {
  font-size: 14px;
  font-weight: 600;
  margin-top: 18px;
  margin-bottom: 18px;
  align-self: flex-start;
}

.orgs-position {
  display: flex;
  flex-direction: row;
  align-items: center;
  margin-bottom: 9px;
}

.orgs-card {
  display: flex;
  flex-direction: column;
  padding: 19px;
  padding-top: 9px;
  box-shadow: 0px 0px 15px rgba(0, 0, 0, 0.1);
  border-radius: 7px;
  height: 100%;
}

.activity-title {
  margin-left: 13px;
}

.orgs-content-wrapper {
  display: flex;
  flex-direction: row;
  align-items: flex-start;
}

.orgs-content {
  display: flex;
  flex-direction: column;
}

.orgs-avatar {
  margin-right: 30px;
  margin-bottom: 20px;
}

.orgs-name {
  font-size: 16px;
  font-weight: 600;
  margin-bottom: 14px;
  line-height: 19px;
}

.orgs-stage-title {
  color: #777F90;
  line-height: 15px;
  margin-bottom: 6px;
}

.orgs-stage {
  font-size: 16px;
  font-weight: 600;
  line-height: 15px;
  margin-bottom: 10px;
}

.orgs-funding-title {
  color: #777F90;
  line-height: 15px;
  margin-bottom: 6px;
}

.orgs-funding {
  font-size: 16px;
  font-weight: 600;
  line-height: 15px;
  display: flex;
  flex-direction: row;
  margin-bottom: 16px;
}

.orgs-description {
  color: #777F90;
}

.orgs-moreinfo {
  color: #4E8EF8;
  text-decoration:underline;
  font-weight: 600;
  margin-top: 8px;
  margin-bottom: 24px;
}

.orgs-menu {
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

.orgs-tags {
  margin-top: 20px;
}

.pillbutton {
  margin-right: 15px;
  margin-bottom: 10px;
}

.orgs-nav {
  margin-top: 24px;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  margin-bottom: 26px;
}

.orgs-nav circle {
  cursor: pointer;
}

.button-chevron {
  color: #4E8EF8;
  width: 20px;
  height: 20px;
  cursor: pointer;
}

</style>
