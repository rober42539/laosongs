<template>
  <div class="home">
    <div v-if="!loading && !installing">
      <h1 class="text-primary" v-html="name"></h1>
      <div class="text-secondary" v-html="description"></div>
    </div>
    <img v-if="!installing" class="logo" src="https://s3-us-west-2.amazonaws.com/laoadventist-media/bible.webp"
    alt="Photo of the Bible by David Ball: www.davidball.net, CC BY 2.5, https://creativecommons.org/licenses/by/2.5/deed.en"/>
    <div class="action" v-if="!loading && !installing">
      <router-link class="btn btn-primary" to="/read">ເປີດ / Open</router-link>
    </div>
  </div>
</template>

<script>
// @ is an alias to /srcS

export default {
  name: 'home',
  computed: {
    name() {
      return this.$store.state.data.title;
    },
    description() {
      return this.$store.state.data.description;
    },
    installing() {
      return this.$store.state.installing;
    },
    loading() {
      return this.$store.state.loading;
    },
  },
};
</script>

<style>
  .logo {
    max-width: 50%;
  }
  .action {
    margin-top: 2rem;
  }
</style>
