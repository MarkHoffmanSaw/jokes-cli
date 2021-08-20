<template>
  <div class="container">
    <div class="card">
      <Jokes />
    </div></div
></template>

<script>
import Jokes from "./components/Jokes";

export default {
  name: "App",
  components: { Jokes },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600&display=swap");

* {
  box-sizing: border-box;
}

body {
  font-family: Inter, Roboto, Oxygen, Fira Sans, Helvetica Neue, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  font-size: 16px;
  color: #08003f;
  background: #ffdc51;
}

hr {
  margin: 1rem 0;
}

strong,
.bold {
  font-weight: 700;
  width: 1000px;
  padding: 0.3rem;
}

ol,
p,
ul {
  line-height: 1.7;
  padding: 0;
  margin: 0;
}

a {
  color: #3eaf7c;
  font-weight: 500;
  text-decoration: none;
}

h1,
h2,
h3,
h4,
h5,
h6 {
  font-weight: 500;
  line-height: 1.45;
}

h1 {
  font-size: 2.2rem;
  font-weight: 600;
}

h2 {
  font-size: 1.65rem;
  padding-bottom: 0.3rem;
  border-bottom: 1px solid #eaecef;
}

h3 {
  font-size: 1.35rem;
  text-align: center;
}

.primary {
  color: #42b983;
}

.danger {
  color: #e53935;
}

.btn {
  color: #42b983;
  position: relative;
  place-content: center;
  place-items: center;
  width: fit-content;
  border-radius: 99px;
  letter-spacing: 0.1em;
  border: 1px solid #42b983;
  text-decoration: none;
  text-transform: uppercase;
  margin-right: 10px;
  padding: 0.5rem 1.5rem;
  white-space: nowrap;
  font-weight: 700;
  outline: none;
  background: #fff;
  transition: all 0.22s;
}

.btn:hover {
  cursor: pointer;
  opacity: 0.8;
}

.btn:disabled {
  cursor: not-allowed;
  opacity: 1 !important;
  background: #eee !important;
  border-color: #ddd !important;
  color: #999 !important;
}

.btn:active {
  box-shadow: inset 1px 1px 1px rgba(0, 0, 0, 0.3);
}

.btn.danger {
  color: #fff;
  border-color: #4f008f;
}

.container {
  margin: 0 auto;
  max-width: 1000px;
}

.container.with-nav {
  margin-top: 70px;
}

.pt-2 {
  padding-top: 2rem;
}

.pt-1 {
  padding-top: 1rem;
}

.pt-5 {
  padding-top: 5rem;
}

.form-control {
  position: relative;
  margin-bottom: 0.5rem;
}

.card {
  overflow: hidden;
  padding: 1rem;
  margin-bottom: 1rem;
  border-radius: 10px;
  box-shadow: 2px 3px 10px rgba(0, 0, 0, 0.2);
  background: #fff;
  text-align: center;
  border: 4px solid #695cbb;
}

.list {
  margin: 0;
  padding: 0;
  list-style: none;
}

.list-item {
  margin: 0.5rem;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0.5rem 0;
  border-radius: 10px;
  transition: 0.22s all;
  text-overflow: ellipsis;
  white-space: pre-line;
  overflow: hidden;
  background-color: beige;
  border: 1px solid #000000;
}

.list-item.liked {
  background-color: rgb(225, 184, 221);
}

.inputValue {
  font-size: large;
  margin-right: 0.5rem;
  margin-left: 0.5rem;
  padding: 0.3rem;
}
</style>
