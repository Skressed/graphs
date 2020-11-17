<template>
  <b-navbar toggleable="true" class="navbar" variant="transparent">
    <b-nav-item class="active" href="#">Мой рабочий стол</b-nav-item>
    <b-nav-item class="unactive" href="#">Картотека</b-nav-item>
    <b-nav-item class="unactive" href="#">Мои чаты</b-nav-item>
    <b-nav-item class="unactive" href="#">Сервисы</b-nav-item>
    <b-navbar-nav class="ml-auto">
      <b-icon class="navicon" icon="wallet2"></b-icon>
      <p class="balance">1590p</p>
      <b-icon class="navicon" icon="book"></b-icon>
      <b-icon class="navicon avatar" icon="person-circle"></b-icon>
      <b-nav-item-dropdown class="dropdown" disabled></b-nav-item-dropdown>
    </b-navbar-nav>
  </b-navbar>

</template>

<script>
export default {
  name: 'Navbar',
}
</script>

<style scoped>
ul, li {
    list-style-type: none;
}

.navbar {
  margin-top: 14px;
  font-size: 16px;
  font-weight: 600;
  width: 75%;
}

a {
  opacity: 0.85;
  transition: 0.5s;
}

.active a {
  color: #111B42;
}

.unactive a {
  color: #BDBDC7;
}

a:hover {
  opacity: 1;
  transition: 0.5s;
  cursor: pointer;
}

p {
  margin: 0; padding: 0;
}

.navbar-nav {
  flex-direction: row;
  align-items: center;
  font-size: 14px;
}

.navicon {
  width: 29px;
  height: 28px;
  color: #E2E2E7;
  opacity: 0.85;
  transition: 0.5s;
}

.navicon:hover {
  opacity: 1;
  transition: 0.5s;
  cursor: pointer;
}

.bi-book {
  margin-left: 40px;
}

.balance {
  margin-left: 12px;
  font-size: 14px;
  color: #111B42;
  font-weight: 600;
  margin-right: 8px;
}

.avatar {
  height: 40px;
  width: 40px;
  margin-left: 40px;
  color: #C4C4C4;
}


</style>
