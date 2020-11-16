<template lang="pug">
  #app
    b-navbar(toggleable='lg' type='dark' variant='info')
      b-navbar-brand(to='/') 番茄鐘
      b-navbar-toggle(target='nav-collapse')
      b-collapse#nav-collapse(is-nav)
        b-navbar-nav
          b-nav-item(to='/list' active-class="active") 待辦
          b-nav-item(to='/settings' active-class="active") 設定
    keep-alive
    router-view
</template>
