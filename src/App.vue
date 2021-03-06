<template>
  <div class="continaer">
    <Header
      @toggle-add-task="toggleAddTask"
      title="Task Tracker"
      :showAddTask="showAddTask"
    />

    <router-view :showAddTask="showAddTask"></router-view>
    <Footer />
  </div>
</template>

<script>
import Header from "./components/Header";
import Footer from "./components/footer";

export default {
  name: "App",
  components: {
    Header,
    Footer,
  },
  data() {
    return {
      showAddTask: false,
    };
  },
  methods: {
    toggleAddTask() {
      this.showAddTask = !this.showAddTask;
    },
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap");
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
html,
body {
  font-family: Arial, Helvetica, sans-serif;
}
.continaer {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  padding: 30px;
  border: 1px solid black;
  border-radius: 5px;
}
#app {
  width: 400px;
  height: 100vh;
  margin: auto;
  text-align: center;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
h1,
h3 {
  margin-bottom: 1rem;
  font-weight: normal;
}
img {
  border-radius: 50%;
  border: 5px #333 solid;
  width: 250px;
  height: 250px;
  margin-bottom: 1rem;
}
.male {
  border-color: steelblue;
  background-color: steelblue;
}
.female {
  border-color: pink;
  background-color: pink;
  color: #333;
}
.btn {
  cursor: pointer;
  display: inline-block;
  background: #333;
  color: white;
  font-size: 18px;
  border: 0;
  margin: 5px;
  border-radius: 8px;
  padding: 1rem 1.5rem;
}
.btn :focus {
  outline: none;
}
.btn :hover {
  transform: scale(0.98);
}
</style>
