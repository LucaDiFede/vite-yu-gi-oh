<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppFooter from './components/AppFooter.vue';
import axios from 'axios';

export default {
  data() {
    return {
        baseUrl: 'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0',
        characters: []
    };
  },
  components: {
    AppHeader,
    AppMain,
    AppFooter
  },
  methods: {

  },
  mounted() {
    axios
      .get(this.baseUrl)
      .then((response) => {
        console.log(response)
        this.characters = response.data.data;
        console.log(this.characters);
    });
  }
}

</script>



<template>

  <AppHeader />

  <AppMain :allCharacters="characters" />

  <AppFooter />
</template>

<style lang="scss">
@use "assets/scss/main" as *;
</style>
