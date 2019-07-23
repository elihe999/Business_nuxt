<template>
  <div class="container">
    <div>
      <!-- <logo /> -->
      <h1 class="title">
        Business_nuxt_frontpage
      </h1>
      <h2 class="subtitle">
        Welcome to the iView + Nuxt.js template
      </h2>
      <ul>
        <li v-for="good in goods" :key="good.id">
          <nuxt-link :to="{name:'detail-id',params:{id: good.id}}">
          <!-- <nuxt-link :to="`/detail/${good.id}`"> -->
            <span>{{good.text}}</span>
            <span>￥{{good.name}}</span>
            <button @click.prevent="addCart(good)">ADD</button>
          </nuxt-link>
        </li>
      </ul>
      <Breadcrumb>
        <BreadcrumbItem to="/">Home</BreadcrumbItem>
        <BreadcrumbItem to="/components/breadcrumb">Components</BreadcrumbItem>
        <BreadcrumbItem>Breadcrumb</BreadcrumbItem>
      </Breadcrumb>
      <nuxt />
    </div>
  </div>
</template>

<script>
// import Logo from '~/components/Logo.vue'
export default {
  head() {
    return {
      title: "calibe",
      meta: [{ name: "description", hid: "description", content: "Calibe shenzhen"}],
      link: [{ rel: "favicon", href: "favicon.ico" }],
    };
  },
  // data() {
  //   return {
  //       goods: [
  //           {id: 1, text:'test1', name:'text1'},
  //           {id: 2, text:'test2', name:'text2'},
  //           {id: 3, text:'test3', name:'text3'}
  //       ]
  //   }
  // },
  async asyncData({$axios, error}) {
    const {ok, goods} = await $axios.$get('/api/goods')
    if (ok) {
      return {goods}
    }
    error({statusCode: 400, message: 'Failed to access data'})
  },
  methods: {
    addCart(){}
  },
  components: {
    // Logo
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}
.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}
.links {
  padding-top: 15px;
}
</style>
