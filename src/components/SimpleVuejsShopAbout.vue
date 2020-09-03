<template>
  <div class="SimpleVuejsShopAbout">
    <h1 class="text-capitalize title">{{ pageData.title }}</h1>
    <div class="offset-3 col-6 content">
      {{ pageData.content }}
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'SimpleVuejsShopAbout',
  data() {
    return {
      pageData: null
    }
  },
  created() {
    axios.get('https://api.jsonbin.io/b/5dd2d56f2e22356f234dcb66/')
      .then(response => this.pageData = response.data.about);
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.SimpleVuejsShopAbout {
  margin: 40px 0;
  font-family: snell
}

.content {
  color: #000;
  font-size: 1.5em;
}
</style>
