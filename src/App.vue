<template>
  <div id="app">
    <div class="d-flex justify-content-center">
      <div class="col-2">
        <form>
          <select class="form-control" v-model="selectedType">
            <option v-for="ty in types" v-bind:value="ty.name" v-bind:key="ty">
              {{ ty.name }}
            </option>
          </select>
          <span>Выбрано: {{ selectedMark }}</span>
          <br />

          <select class="form-control" v-model="selectedMark">
            <option
              v-for="mark in marks[selectedType]"
              :value="mark.name"
              v-bind:key="mark"
            >
              {{ mark.name }}
            </option>
          </select>
          <span>Выбрано: {{ selectedMark }}</span>
          <br />

          <select class="form-control" v-model="selectedModel">
            <option
              v-for="model in models[selectedMark]"
              v-bind:value="model.name"
              v-bind:key="model"
            >
              {{ model.name }}
            </option>
          </select>
          <span>Выбрано: {{ selectedModel }}</span>
          <br />
          <button class="btn btn-primary" type="submit">Ok</button>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      types: [{ name: "light" }, { name: "heavy" }],
      selectedType: "",

      marks: {
        light: [{ name: "reno" }],
        heavy: [{ name: "kraz" }],
      },
      selectedMark: "",

      models: {
        reno: [{ name: "clio" }],
        kraz: [{ name: "vepr" }],
      },
      selectedModel: "",
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
