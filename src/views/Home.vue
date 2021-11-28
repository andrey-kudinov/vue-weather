<template>
  <div class="page">
    <div class="page__top">
      <button class="button page__add" @click="add">+</button>
    </div>

    <div class="page__blocks">
      <div class="page__block" v-for="block in blocks" :key="block.id">
        <div class="page__input-container">
          <input type="text" class="page__input" />
          <button class="button page__search">Search</button>
        </div>

        <div class="page__result">Result</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      blocks: [
        {id: 1},
        {id: 2},
        {id: 3}
      ]
    }
  },
  methods: {
    add() {
      this.blocks.push({id: new Date()})
    },
  },
};
</script>

<style scoped>
.page {
  display: grid;
  place-items: center;
  min-height: 100vh;
  background-color: #000;
}

.page__top {
  color: white;
}

.page__add {
  width: 3rem;
  height: 3rem;
  padding: 0;
  font-size: 1.5rem;
}

.page__blocks {
  display: grid;
  gap: 1rem;
}

.page__block {
  display: flex;
  align-items: center;
}

.page__input {
  margin-right: 1rem;
}

.page__result {
  color: white;
}
</style>
