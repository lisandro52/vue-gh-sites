<template>
  <div>
    <h1>Acá tengo que cargar el {{ $route.params.page }}</h1>
    <vue-markdown :source="asdf"></vue-markdown>
  </div>
</template>

<script>
  import axios from 'axios'
  import VueMarkdown from 'vue-markdown'

  export default {
    mounted: function() {
      axios.get('https://raw.githubusercontent.com/lisandro52/vue-ghpages-cms/master/contact.md')
        .then((response)=>{
          this.markdown = response.data;
        });
    },
    data: ()=>({
      markdown: ""
    }),
    components: {
      VueMarkdown
    }
  }
</script>