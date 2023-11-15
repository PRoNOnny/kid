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
  color: rgb(242, 104, 175);
  height: .8rem;
  margin-right: 3px;
}


.nav {
  background-color: #ffffff;
  justify-content: space-evenly;
  align-content: center;
  height: 4rem;
  margin-bottom: 2rem !important;
  
}

.nav a {
  font-size: small;
  color: rgb(233, 188, 243);
  text-decoration: none;
  display: flex;
  align-items: center;
}

.nav a.router-link-exact-active {
  color: white;  
}

.nav a:hover {
  color: rgb(242, 104, 175);
}

.nav a:focus {
  color: rgb(242, 104, 175);
}

</style>
