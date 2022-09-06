<template>
  <div class="text-field">
    <label class="text-field__label" :class="{ error: hasError }" for="s1">{{ msg }}</label>
    <div :style="{ position: 'relative' }">
      <input
        type="text"
        class="text-field__input"
        :class="{ disable: isDisabled, locked: isLocked, error: hasError }"
        name="s1"
        id="s1"
        :readonly="isLocked"
        placeholder="Введите тип"
        v-model="textValue"
        :disabled="isDisabled"
        value="Федеральный проект"
        @focus="setFocus"
        @blur="setBlur"
      />
      <div class="text-field__clear-button" @click="clearField" />
      <div
        class="text-field__error-warning"
        :class="{ active: hasError }"
        v-show="hasError"
      ></div>
    </div>
    <div class="text-field__error" v-show="hasError">{{ errorMsg }}</div>
  </div>
</template>

<script>
export default {
  name: "MyInput",
  props: {
    msg: String,
    isDisabled: Boolean,
    typeOfInput: String,
    isLocked: Boolean,
  },
  data() {
    return {
      focused: false,
      textValue: "",
      hasError: false,
      errorMsg: "",
    };
  },
  methods: {
    clearField() {
      this.textValue = "";
    },
    setFocus() {
      this.focused = true;
      if (this.textValue === 'Smth') {
        this.errorMsg = "";
        this.hasError = false;
      }
    },
    setBlur() {
      this.focused = false;
      if (this.textValue === 'Smth') {
        this.errorMsg = "Error!";
        this.hasError = true;
      }
    },
    hideClearButton() {
      this.focused = false;
    },
  },
};
</script>

<style>
*,
*::before,
*::after {
  box-sizing: border-box;
}
@font-face {
  font-family: SegoeUI;
  src: local("Segoe UI"),
    url(//c.s-microsoft.com/static/fonts/segoe-ui/west-european/normal/latest.woff2)
      format("woff2"),
    url(//c.s-microsoft.com/static/fonts/segoe-ui/west-european/normal/latest.woff)
      format("woff"),
    url(//c.s-microsoft.com/static/fonts/segoe-ui/west-european/normal/latest.ttf)
      format("truetype");
  font-weight: 400;
}
@font-face {
  font-family: SegoeUI;
  src: local("Segoe UI Semibold"),
    url(//c.s-microsoft.com/static/fonts/segoe-ui/west-european/semibold/latest.woff2)
      format("woff2"),
    url(//c.s-microsoft.com/static/fonts/segoe-ui/west-european/semibold/latest.woff)
      format("woff"),
    url(//c.s-microsoft.com/static/fonts/segoe-ui/west-european/semibold/latest.ttf)
      format("truetype");
  font-weight: 700;
}

.text-field__input {
  display: block;
  width: 281px;
  height: calc(2.25rem + 2px);
  padding: 10px 8px;
  padding-right: 25px;
  font-family: inherit;
  font-size: 1rem;
  font-weight: 400;
  line-height: 1.5;
  color: #081735;
  background-color: #fff;
  border: 0.5px solid #8f95b2;
  border-radius: 4px;
}
.text-field__input:hover {
  border: 0.5px solid #1b88d1;
}
.text-field__input:focus {
  border: 1px solid #1b88d1;
  outline: none;
}
.text-field__input:focus ~ .text-field__clear-button {
  opacity: 1;
}

.text-field {
  margin-bottom: 1rem;
  display: flex;
  justify-content: flex-start;
  flex-direction: column;
}
.text-field__label {
  display: block;
  margin-bottom: 0.25rem;
  height: 16px;
  font-family: "Segoe UI";
  font-style: normal;
  font-weight: 400;
  color: #8f95b2;
  width: fit-content;
}

.text-field__clear-button {
  opacity: 0;
  background-image: url("../assets/Vector.svg");
  background-repeat: no-repeat;
  position: absolute;
  top: 14px;
  right: 9px;
  width: 10px;
  height: 10px;
}

.text-field__error {
  align-self: flex-end;
  font-size: 12px;
  color: red;
  line-height: 16px;
}
.text-field__error-warning {
  opacity: 0;
  background-image: url("../assets/Error.svg");
  background-repeat: no-repeat;
  position: absolute;
  top: 10px;
  right: 11px;
  width: 13px;
  height: 20px;
}
.active {
  opacity: 1;
}
.disable {
  background: #f4f4f4;
  color: #8f95b2;
  cursor: not-allowed;
}
.disable::placeholder {
  color: #8f95b2;
}
.locked, .locked:hover, .locked:focus {
  border: none;
}
.locked:focus ~ .text-field__clear-button {
  display: none;
}
.error {
  border-color: red;
  color: red;
}
</style>