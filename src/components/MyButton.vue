<template>
  <button :class="typeOfButton" :disabled="isDisabled">
    <svg
      v-if="typeOfButton === 'normalWithIcon'"
      width="15"
      height="14"
      viewBox="0 0 15 14"
      fill="#1B88D1"
      xmlns="http://www.w3.org/2000/svg"
    >
      <path
        d="M6.71053 2H8.28947C8.42982 2 8.5 2.03704 8.5 2.11111V11.8889C8.5 11.963 8.42982 12 8.28947 12H6.71053C6.57018 12 6.5 11.963 6.5 11.8889V2.11111C6.5 2.03704 6.57018 2 6.71053 2Z"
        fill="#1B88D1"
      />
      <path
        d="M2.61628 6H12.3837C12.4612 6 12.5 6.07018 12.5 6.21053V7.78947C12.5 7.92982 12.4612 8 12.3837 8H2.61628C2.53876 8 2.5 7.92982 2.5 7.78947V6.21053C2.5 6.07018 2.53876 6 2.61628 6Z"
        fill="#1B88D1"
        
      />
    </svg>
    {{ msg }}
  </button>
</template>

<script>
export default {
  name: "MyButton",
  props: {
    msg: String,
    isDisabled: Boolean,
    typeOfButton: String,
  },
  data() {
    return {
      isActive: false,
    };
  },
};
</script>

<style>
@font-face {
    font-family: SegoeUI;
    src:
        local("Segoe UI"),
        url(//c.s-microsoft.com/static/fonts/segoe-ui/west-european/normal/latest.woff2) format("woff2"),
        url(//c.s-microsoft.com/static/fonts/segoe-ui/west-european/normal/latest.woff) format("woff"),
        url(//c.s-microsoft.com/static/fonts/segoe-ui/west-european/normal/latest.ttf) format("truetype");
    font-weight: 400;
}
@font-face {
    font-family: SegoeUI;
    src:
        local("Segoe UI Semibold"),
        url(//c.s-microsoft.com/static/fonts/segoe-ui/west-european/semibold/latest.woff2) format("woff2"),
        url(//c.s-microsoft.com/static/fonts/segoe-ui/west-european/semibold/latest.woff) format("woff"),
        url(//c.s-microsoft.com/static/fonts/segoe-ui/west-european/semibold/latest.ttf) format("truetype");
    font-weight: 700;
}
button {
  display: flex;
  align-items: center;
  column-gap: 6px;
}
.primary {
  color: white;
  height: 32px;
  border: 1px solid #1b88d1;
  box-shadow: 0px 8px 16px rgba(143, 149, 178, 0.15);
  border-radius: 6px;
  padding: 7px, 20px, 8px, 20px;
  background: #1b88d1;
  border: 1px solid #1b88d1;
  font-family: "Segoe UI";
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
}
.primary:hover {
  box-shadow: 0px 4px 16px rgba(27, 136, 209, 0.25);
}
.primary:focus {
  box-shadow: none;
  border: 1px solid #154e9b;
}
.primary:active {
  background: #154e9b;
  box-shadow: none;
  border: 1px solid #154e9b;
}
.primary:disabled {
  background: #caccd6;
  border: 1px solid #caccd6;
  box-shadow: none;
}

.outline {
  color: #1b88d1;
  height: 32px;
  border: 1px solid #1b88d1;
  box-shadow: 0px 8px 16px rgba(143, 149, 178, 0.15);
  border-radius: 6px;
  padding: 7px, 20px, 8px, 20px;
  background: #ffffff;
  border: 1px solid #1b88d1;
  font-family: "Segoe UI";
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
}
.outline:hover {
  box-shadow: 0px 4px 16px rgba(27, 136, 209, 0.25);
}
.outline:focus {
  box-shadow: none;
  border: 1px solid #154e9b;
}
.outline:active {
  background: #85c8fd;
}
.outline:disabled {
  background: #ffffff;
  border: 1px solid #caccd6;
  color: #caccd6;
  box-shadow: none;
}

.normalWithIcon {
  color: #1b88d1;
  height: 32px;
  border: 1px solid #1b88d1;
  box-shadow: 0px 8px 16px rgba(143, 149, 178, 0.15);
  border-radius: 6px;
  padding: 7px, 20px, 8px, 20px;
  background: #ffffff;
  border: 1px solid #1b88d1;
  font-family: "Segoe UI";
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
}
.normalWithIcon:hover {
  box-shadow: 0px 4px 16px rgba(27, 136, 209, 0.25);
}
.normalWithIcon:focus {
  box-shadow: none;
  border: 1px solid #154e9b;
}
.normalWithIcon:active {
  background: #85c8fd;
}
.normalWithIcon:disabled {
  background: #ffffff;
  border: 1px solid #caccd6;
  color: #caccd6;
  box-shadow: none;
}
.normalWithIcon:disabled svg path {
  fill: #caccd6;
}

.link {
  padding: 0;
  margin: 0;
  background: none;
  border: none;
  color: #1b88d1;
  font-family: "Segoe UI";
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 20px;
  height: 20px;
}
.link:hover {
  font-weight: 700;
}
.link:focus {
  font-weight: 700;
}
.link:active {
  font-weight: 700;
  color: #154E9B;
}
.link:disabled {
  font-weight: 400;
  color: #8F95B2;
}
</style>