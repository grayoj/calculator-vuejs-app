<template>
  <div>
    <b-navbar toggleable="sm" type="light" variant="light">
    <b-navbar-toggle target="nav-text-collapse"></b-navbar-toggle>

    <b-navbar-brand>Simple Calculator in VueJS</b-navbar-brand>

    <b-collapse id="nav-text-collapse" is-nav>
      <b-navbar-nav>
        <b-nav-text>Enjoy</b-nav-text>
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
  </div>
</template>

<script>
export default {
    name: 'MyNavigation',
    props: {
    msg: String
  },
}
</script>

<style scoped>

</style>