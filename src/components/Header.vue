<template>
  <nav class="navbar navbar-light fixed-top bg-faded mb-3">
    <div class="container d-flex">
      <a class="navbar-brand" href="#">
        <img class="logo" src="https://static.galileo.xiaojukeji.com/static/tms/shield/z/mofang/mofang/images/mofang_logo.png" alt="Cube's logo" height="24"> Issue Helper</a>

      <ul class="navbar-nav ml-auto d-flex flex-row">
        <li v-for="(locale, _lang) in $root.$locales" class="nav-item px-2">
          <a class="nav-link ml-auto"
            :class="{ active: lang ===  _lang }"
            @click="$emit('change-lang', _lang)">
            {{ locale._label }}
          </a>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script>
import locales from '../i18n/locales/index'

export default {
  props: ['lang']
}
</script>

<style lang="scss">
.navbar {
  border-bottom: 1px solid #eee;
}


.logo {
 margin-right: 5px
}

.nav-link {
  cursor: pointer;
  &.active {
    color: #4fc08d !important;
    // font-weight: bold;
  }
}
</style>
