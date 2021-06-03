/* eslint-disable no-unused-vars */
<template>
 <v-container>
    <div class="home">
        <h1 class="pink accent-1 black--text"> Data?</h1>
        <p></p>
        <v-btn  elevation="2" color="pink lighten-4 white--text" >Yes
            <v-icon>mdi-checkbox-marked-circle</v-icon> </v-btn>
        &nbsp;&nbsp;&nbsp;
        <v-btn  elevation="2" color="red darken-4 white--text" >
            No <v-icon>mdi-cancel</v-icon></v-btn>
        
<p/>
<p/>
<v-data-table
    :headers="headers"
    :items="desserts"
    :items-per-page="5"
    class="elevation-1"
  >
  {{ABD}}
  <tr>
  <td>ID</td>
  <td>Name</td>
  <td>Age</td>
  <td>Tel</td>
  <td>Email</td>
  </tr>
  <tr v-for="item in list" v-bind:key="item.id">
  <td>{{item.EMP_ID}}</td>
  <td>{{item.Name}}</td>
  <td>{{item.Age}}</td>
  <td>{{item.Tel}}</td>
  <td>{{item.Email}}</td>
  </tr></v-data-table>
  
    </div> 
 </v-container>
</template>

<script>
import vue from 'vue';
//import vueaxios from 'vue-axios'

//vue.use(vueaxios.axios)
  export default {
    name:"acompany",
    data(){
    return {list:undefined}
    },
    mounted()
    {
     vue.axios.get('http://localhost:3000/acompany').then((resp)=>{
        this.list=resp.data.data;
        console.log(resp.data.data)
      })
    }
  }
</script>
