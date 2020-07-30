<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
  export default {
    name: 'app'
  }
</script>

<style lang="scss">

  /* reset */
  html {
    -webkit-text-size-adjust: none;
    -webkit-user-select: none;
    -webkit-touch-callout: none;
    font-family: Helvetica;
  }

  body {
    font-size: 12px;
  }

  body,
  h1,
  h2,
  h3,
  h4,
  h5,
  h6,
  p,
  dl,
  dd,
  ul,
  ol,
  pre,
  form,
  input,
  textarea,
  th,
  td,
  select {
    margin: 0;
    padding: 0;
    font-weight: normal;
    text-indent: 0;
  }

  a,
  button,
  input,
  textarea,
  select {
    background: none;
    -webkit-tap-highlight-color: rgba(255, 0, 0, 0);
    outline: none;
    -webkit-appearance: none;
  }

  em {
    font-style: normal;
  }

  li {
    list-style: none;
  }

  a {
    text-decoration: none;
  }

  img {
    border: none;
    vertical-align: top;
  }

  table {
    border-collapse: collapse;
  }

  textarea {
    resize: none;
    overflow: auto;
  }

  /* end reset */

  ol,
  ul {
    list-style: none;
  }

  blockquote,
  q {
    quotes: none;
  }

  blockquote:before,
  blockquote:after,
  q:before,
  q:after {
    content: '';
    content: none;
  }

  table {
    border-collapse: collapse;
    border-spacing: 0;
  }

  /* iphonex 兼容方案
  https://aotu.io/notes/2017/11/27/iphonex/index.html */

  /* iphonex 安全区域 */
  body {
    margin: 0;
    overflow-x: hidden;
    background-color: #fff !important;
    padding-bottom: constant(safe-area-inset-bottom);
    padding-bottom: env(safe-area-inset-bottom);
  }

  /* iphonex fix底部元素适配 */
  :global(.fixed_bottom) {
    padding-bottom: constant(safe-area-inset-bottom);
    padding-bottom: env(safe-area-inset-bottom);
    position: fixed;
    z-index: 10;
    background-color: #fff;
  }

  html,
  body,
  #app {
    width: 100%;
    height: 100%;
    font-family: Avenir, Helvetica, Arial, sans-serif;
    text-align: center;
  }
</style>
