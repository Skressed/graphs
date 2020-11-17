<template>
  <div class="maininfo">
    <div class="maininfo-content-wrapper">
      <div class="maininfo-content-left">
        <img class="profpic" src="../assets/profpic.svg">
        <div class="menu">
          <b-icon class="menu-icon" icon="bookmark"></b-icon>
          <b-icon class="menu-icon" icon="pencil-square"></b-icon>
          <b-icon class="menu-icon" icon="person-plus"></b-icon>
          <b-icon class="menu-icon" icon="share"></b-icon>
        </div>
      </div>
      <div class="maininfo-content">
        <p class="maininfo-content-initials">Петров Владимир Викторович</p>
        <div class="maininfo-content-titles">
          <img src="../assets/pro-user.svg">
          <img src="../assets/verified.svg">
        </div>
        <div class="maininfo-roles">
          <p class="roles-title">Роли на платформе</p>
          <p class="role">Представитель компании</p>
          <p class="role-caption">Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Maininfo',
}
</script>

<style scoped>
.maininfo {
    padding-left: 33px;
}
.menu {
  margin-top: 30px;
  width: 181px;
  display: flex;
  justify-content: space-between;
}

.menu-icon {
  width: 25px; height: 25px;
  color: #BDBDC7;
  transition: 0.5s;
  opacity: 0.6;
}

.menu-icon:hover {
  opacity: 1;
  transition: 0.5s;
  cursor: pointer;
}

.profpic {
  margin-top: 8px;
  width: 181px;
  height: 182px;
}

.maininfo-content-wrapper {
  display: flex;
  flex-direction: row;
}

.maininfo-content {
  display: flex;
  flex-direction: column;
  margin-left: 31px;
}

.maininfo-content-initials {
  font-size: 25px;
  font-weight: 600;
}

.maininfo-content-titles {
  display: flex;
  flex-direction: row;
}

.maininfo-content-titles img {
  margin-right: 11px;
  margin-bottom: 20px;
}

.maininfo-roles {
  display: flex;
  flex-direction: column;
}

.roles-title {
  font-size: 16px;
  font-weight: 600;
}

.role, .role-caption {
  font-size: 14px;
  color: #777F90;
}

</style>
