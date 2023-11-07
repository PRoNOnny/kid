<template>
  <BNav>
    <router-link to="/"><BNavItem><i-mdi-home/> Home</BNavItem></router-link>
    <router-link to="/brand"><BNavItem><i-mdi-TshirtCrew/> Brand</BNavItem></router-link>
    <router-link to="/order"><BNavItem><i-mdi-cart/> Order</BNavItem></router-link>
  </BNav>
  
  <router-view></router-view>
</template>

<style>
svg {
  color: darkgoldenrod;
  height: .8rem;
  margin-right: 3px;
}

.nav {
  background-color: #06192c;
  justify-content: space-evenly;
  align-content: center;
  height: 4rem;
  margin-bottom: 2rem !important;
}

.nav a {
  font-size: small;
  color: gainsboro;
  text-decoration: none;
  display: flex;
  align-items: center;
}

.nav a.router-link-exact-active {
  color: white;
}
</style>
