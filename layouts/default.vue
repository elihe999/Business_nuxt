<template>
  <div>
    <i-menu mode="horizontal" :theme="menuTheme" active-name="1" @on-select="onMenuSelect">
      <Menu-Item name="1">
        <Icon type="ios-paper"></Icon>News
      </Menu-Item>
      <Menu-Item name="2">
        <Icon type="ios-people"></Icon>Business
      </Menu-Item>
      <Submenu name="3">
        <template slot="title">
          <Icon type="stats-bars"></Icon>Product
        </template>
        <Menu-Group title="1">
          <Menu-Item name="3-1">11</Menu-Item>
          <Menu-Item name="3-2">12</Menu-Item>
          <Menu-Item name="3-3">13</Menu-Item>
        </Menu-Group>
        <Menu-Group title="2">
          <Menu-Item name="3-4">21</Menu-Item>
          <Menu-Item name="3-5">22</Menu-Item>
        </Menu-Group>
      </Submenu>
      <Menu-Item name="4">
        <Icon type="settings"></Icon>http://wallimn.iteye.com
      </Menu-Item>
    </i-menu>
    <nuxt />
    <nav>
      <nuxt-link to="/">Home</nuxt-link>
      <NLink to="/admin">Admin</NLink>
      <n-link to="/cart">Cart</n-link>
    </nav>
  </div>
</template>

<style>
html {
  font-family: "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI",
    Roboto, "Helvetica Neue", Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}

.button--green {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #3b8070;
  color: #3b8070;
  text-decoration: none;
  padding: 10px 30px;
}

.button--green:hover {
  color: #fff;
  background-color: #3b8070;
}

.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--grey:hover {
  color: #fff;
  background-color: #35495e;
}
</style>
