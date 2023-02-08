<script >
export default{
  data(){
    return{
      msg:'YOYO',
      data:{},
    }
  },
  mounted(){
    console.log(import.meta.env.VITE_TEXT) // 123
    console.log(import.meta.env.VITE_PATH)
    this.axios.get('https://randomuser.me/api/')
      .then((res)=>{
        console.log(res);
        this.data = res.data.results[0]
        console.log(this.data);
      })
  }
}
</script>

<template>
  <div class="greetings">
    <h1 class="green">{{ msg }}</h1>
    <p>HI! I'm  {{ data.gender }}</p>
    <h3>
      You’ve successfully created a project with
     
      <a href="https://vitejs.dev/" target="_blank" rel="noopener">Vite</a> +
      <a href="https://vuejs.org/" target="_blank" rel="noopener">Vue 3</a>.
    </h3>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
