<template>
  <div>
    <h2>Hello, World!</h2>
    <form @submit.prevent="route()">
      <input 
        v-model="q"
        type="text">
      <button>검색 페이지로</button>  
      <pre>{{$data}}</pre>
      <input v-model="width"> {{width}}
      <ol>
        <li>{{computedData}}</li>
        <li>{{computedData}}</li>
      </ol>        
      <ol>
        <li>{{methodsData()}}</li>
        <li>{{methodsData()}}</li>
      </ol>        
    </form>
    <!-- <nuxt-link to="/search">검색 페이지로</nuxt-link>   -->
  </div>
</template>

<script>
export default {
  data: _ => ({
    q: '',
    width: 800,
    height: 600,
  }),
  computed: {

    halfWidth : {
      get() {return this.width / 2},
      set(val) { this.width = val * 2},
    },

    halfHeight() {
      return this.height / 2;
    },

    computedData() {return Math.random()}
  },

  beforeCreate() {
    // alert('beforeCreate');
  },
  create() {
    // alert('create');
  },
  beforeMount() {
    // alert('beforeMount');
  },
  mounted() {
    
    // alert('mounted');
  },
  beforeUpdate() {
    // alert('beforeUpdate');
  },
  updated() {
    // alert('updated');
  },
  beforeDestroy() {
    // alert('beforeDestroy');
  },
  destroyed() {
    // alert('destroyed');
  },
  errorCaptured() {
    // alert('errorCaptured');
  },

  methods: {
    route() {
      this.halfWidth = 100;
      console.log(this.$el);
      console.log(this.$data);
      // if(this.q.length < 2) return alert('검색어는 2글자 이상')

      // this.$router.push('/search');
    },

    methodsData() {return Math.random()}
  },
  
}
</script>