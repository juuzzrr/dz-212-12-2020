<template>
  <div id="app">
    <UserCard v-bind:cat="cat"></UserCard>
  </div>
</template>

<script>
import UserCard from "./components/UserCard.vue";
export default {
  name: "app",
  components: {
    UserCard
  },
  data(){
    return {
      info: [],
    };
    },
    methods:{
    updFact(){
      this.axios
      .get("http://188.225.47.187/api/cats/random-fact.php")
      .then( (response)=>{
          this.info=response.data;
        }
    )
  }
},
mounted(){
  this.updFact();
}
};
</script>
