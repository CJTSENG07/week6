<template>
  <h1>這使前台</h1>
  <nav>
    <RouterLink to="/">Home</RouterLink> |
    <RouterLink to="/about">About</RouterLink> |
    <RouterLink to="/products">products</RouterLink> |
    <RouterLink to="/cart">cart</RouterLink>|
    <RouterLink to="/login">Login</RouterLink>|
    <RouterLink to="/admin/products">後台 購物車列表</RouterLink>
  </nav>
  <router-view></router-view>
</template>
