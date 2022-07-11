<template>
  <div class="footerbox">
    <div class="link-container">
      <NuxtLink to="/">Home</NuxtLink>
      <NuxtLink to="/time">Time Tracker</NuxtLink>
    </div>

    <div class="link-container">
      <NuxtLink to="/todo">To Do List</NuxtLink>
      <NuxtLink to="/notes">Personal Notes</NuxtLink>
    </div>

    <div class="link-container">
      <NuxtLink to="/goals">Goals</NuxtLink>
      <NuxtLink to="/dashboard">Dashboard</NuxtLink>
    </div>
  </div>
</template>



<style lang="scss" scoped>
.footerbox {
  width: 100%;
  min-height: 150px;
  background-color: #3b847f;

  display: flex;
  justify-content: center;
  padding: 70px;

  @media (max-width: 500px) {
    flex-direction: column;
    padding: 45px;
  }

  .link-container {
    display: flex;
    flex-direction: column;

    & + .link-container {
      margin-top: 15px;

      @media (min-width: 500px) {
        margin-left: 150px;
        margin-top: 0;
      }
    }

    a {
      color: #fff;
      text-decoration: none;
      
      & + a {
        margin-top: 15px;
      }
    }
  }
}
</style>