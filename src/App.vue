<template>
  <div id="app">
    <Header></Header>
    <HeaderSlider></HeaderSlider>
    <content>
      <div class="container">
        <Content></Content>
      </div>
    </content>
    <footer class="footer">
      <Footer></Footer>
    </footer>
  </div>
</template>

<script>
  import 'bootstrap';
  import 'bootstrap/dist/css/bootstrap.min.css';
  import './assets/sass/style.sass';
  import Header from './components/Header.vue';
  import HeaderSlider from './components/HeaderSlider.vue';
  import Content from './components/Content.vue';
  import Footer from './components/Footer.vue';


export default {
  name: 'App',
  components: {
    Header, HeaderSlider, Content, Footer
  }
}
</script>