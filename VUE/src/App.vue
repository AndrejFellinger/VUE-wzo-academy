<template>
  <section>
    <h1>Nova polozka</h1>
    <section class="inputs bg">
      <p>Nazov polozky</p>
      <input v-model="input" placeholder="vajce">
      <button @click="pridatItem()">pridat</button>
    </section>

    <section class="aktualne bg">
      <h2>Polozky</h2>
      <ul>
        <li v-for="item in items" :key="`item-${item.id}`">{{item}}</li>
      </ul>
    </section>

    <section class="zmazane bg">
      <h2>Zmazane</h2>
      <ul>
        <li v-for="zmazana in zmazane">{{zmazana}}</li>
      </ul>
    </section>
  </section>
</template>

<script>
export default {
  data() {
    return {
      input: '',
      items: [null],
      zmazane: [null]
    }
  },
  methods: {
    pridatItem() {
      this.items.push({
        text: this.input,
        id: this.items.length + 1,
        is_deleted: false
        })
      this.input = ''
    }
  },
}
</script>

<style scoped>
  .inputs {
    display: grid;
  }

  .inputs button {
    background: green;
  }

  .bg{
    background: rgb(23, 23, 23);
    border-radius: 3px;
    padding: 10px;
    margin: 4px;
  }
</style>