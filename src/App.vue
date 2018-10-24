<template>
  <div id="app">
    <h1>V-neck LLC Name Generator</h1>
    <div v-if="showName" class="company-name">
      <div class="img-wrapper">
        <img alt="Vue logo" src="./assets/logo.png"><span class="img-text">{{ stripped }}</span>
      </div>
      <HelloWorld msg="LLC"/>
    </div>
    <div v-else="showName">
      <label>LLC Name</label><br />
      <input v-model="companyName" type="text" placeholder="Enter desired LLC Name..." /><br />
      <button @click.prevent="toggleInput">Generate LLC Name</button>
    </div>
    <button @click.prevent="toggleInput" v-if="showName">Enter New Name</button>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'app',
  data: () => (
  {
      companyName: "",
      showName: false
  }),
  components: {
    HelloWorld
  },
  computed: {
    stripped() {
      return this.companyName.split('').filter((l,i) => i != 0).join('')
    }
  },
  methods: {
    toggleInput() {
      this.showName = !this.showName
      if(!this.showName) {
        this.companyName = ""
      }
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  width: 80%;
  margin-right: auto;
  margin-left: auto;
  min-height: 500px;
  border: 1px solid black;
  border-radius: 25px;
}

.img-wrapper {
  display: flex;
  margin: auto;
  justify-content: center;
}

.img-text {
  font-size: 25px;
  align-self: flex-end;
  margin-left: -75px;
  margin-bottom: 3px;
}

.company-name {
  display: grid;
  grid-template-columns: 100%;
  align-content: center;
}
</style>
