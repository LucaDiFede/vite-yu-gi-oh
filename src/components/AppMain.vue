<script>

export default {
  data() {
    return {

    };
  },
  methods: {

  },
  props: {
      allCharacters: Array
  }
}
</script>

<template>
  <main>
    <div class="container" style="background-color: orange; padding: 30px;">
      <select>
        <option value="Alien">
          Alien
        </option>
      </select>
      <div class="row" style="background-color: white;">
        <div class="col-12 col-sm-6 col-md-3 text-center"
        v-for="(character, i) in allCharacters"
        :key="i">
        <div class="single-character">
          <div>
            <img :src="character.card_image" :alt="character.name">
          </div>
          <div>
            <h2 class="mb-3 fs-5">
              {{ character.name }}
            </h2>
            <h4 class="fs-6">
              {{  character.species }}
            </h4>
          </div>
        </div>
      </div>
    </div>
   </div>
  </main>
</template>

<style lang="scss" scoped>
</style>