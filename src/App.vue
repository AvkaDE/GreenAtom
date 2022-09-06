<template>
  <div id="app">
    <HelloWorld msg="GreenAtom UI-kit" />
    <p>Buttons</p>
    <div
      :style="{
        display: 'flex',
        flexDirection: 'row',
        gap: '20px',
        justifyContent: 'center',
      }">
      <my-button msg="Primary" :isDisabled="false" typeOfButton="primary" />
      <my-button msg="Primary" :isDisabled="true" typeOfButton="primary" />
      <my-button msg="Outline" :isDisabled="false" typeOfButton="outline" />
      <my-button msg="Outline" :isDisabled="true" typeOfButton="outline" />
      <my-button
        msg="Outline"
        :isDisabled="false"
        typeOfButton="normalWithIcon"
      />
      <my-button
        msg="Outline"
        :isDisabled="true"
        typeOfButton="normalWithIcon"
      />
      <my-button msg="Outline" :isDisabled="false" typeOfButton="link" />
      <my-button msg="Outline" :isDisabled="true" typeOfButton="link" />
    </div>
    <p>Input</p>
    <div
      :style="{
        display: 'flex',
        flexDirection: 'row',
        gap: '20px',
        justifyContent: 'center',
      }">
      <my-input msg="Тип" :isDisabled="false" :isLocked="false" typeOfInput="textBox"/>
      <my-input msg="Тип" :isDisabled="true" :isLocked="false" typeOfInput="textBox"/>
      <my-input msg="Тип" :isDisabled="false" :isLocked="true" typeOfInput="textBox"/>
    </div>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import MyButton from "./components/MyButton.vue";
import MyInput from './components/MyInput.vue';

export default {
  name: "App",
  components: {
    HelloWorld,
    MyButton,
    MyInput,
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
