<template>
  <div class="">
    <h2 class="center">{{titulo}}</h2>
    <form class="" style="margin-top: 30px">
      <div class="form-group">
        <label for="firstname">Nombre del Actor</label>
        <input type="text" v-model="actor.firstName" class="form-control" id="firstname" aria-describedby="" placeholder="">
      </div>
      <div class="form-group">
        <label for="lastname">Apellido del actor</label> <br>
        <input type="text" v-model="actor.lastName" class="form-control" id="lastname" aria-describedby="" placeholder="">
      </div>
      <button v-on:click.prevent="post" class="btn btn-primary">Agregar</button>
    </form>
  </div>
</template>
<script>
export default {
  data(){
    return{
      actor:{
        firstName: '',
        lastName: '',
        lastUpdate: new Date()
      },
      titulo: 'Agrega un actor'
    }
  },
  methods:{
    post:function(){
      this.$http.post('http://localhost:8081/sakila-spring-backend/actors',{
        firstName: this.actor.firstName,
        lastName: this.actor.lastName,
        lastUpdate: this.actor.lastUpdate
      }).then(function(data){
        console.log(data);
      });
    }
  }
}
</script>
