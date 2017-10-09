<template>
  <div class="hello">
    <h1>{{ 1111111111111111 }}</h1>
    <h2>Essential Links</h2>
    <ul>
      <li><a href="https://vuejs.org" target="_blank">Core Docs</a></li>
      <li><a href="https://forum.vuejs.org" target="_blank">Forum</a></li>
      <li><a href="https://chat.vuejs.org" target="_blank">Community Chat</a></li>
      <li><a href="https://twitter.com/vuejs" target="_blank">Twitter</a></li>
      <br>
      <li><a href="http://vuejs-templates.github.io/webpack/" target="_blank">Docs for This Template</a></li>
    </ul>
    <h2>Ecosystem</h2>
    <ul>
      <li><a href="http://router.vuejs.org/" target="_blank">vue-router</a></li>
      <li><a href="http://vuex.vuejs.org/" target="_blank">vuex</a></li>
      <li><a href="http://vue-loader.vuejs.org/" target="_blank">vue-loader</a></li>
      <li><a href="https://github.com/vuejs/awesome-vue" target="_blank">awesome-vue</a></li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      config: {
          headers: {'Content-Type': 'application/x-www-form-urlencoded'
          }
    }
  }
},methods: {
      testGet: function(){
          // axios.get('http://rest/user6/rest_task1/client/api/cars/1', this.config)
          axios.get('http://192.168.0.15/~user15/REST/client/api/cars/', this.config)
            .then(function (response) {
            console.log(response.data);
        })
        .catch(function (error) {
          console.log(error);
        });
      },
      testPost: function()
      {
        //var data = new FormData();
        //data.append('login', 'aaaaaa');
        //data.append('pass', '123456');
        // axios.post('http://rest/user6/rest_task1/client/api/users/', data, this.config)
        var data = {
          "id_car":'1',
          "login":'blue',
          "password":'111',
          "payment_method":'cash'
        }
        axios.post('http://192.168.0.15/~user15/REST/client/api/order/', data, this.config)
        .then(function (response) {
          console.log(response);
        })
        .catch(function (error) {
          console.log(error);
        });
      },
      testPut: function()
      {
        // axios.put('http://rest/user6/rest_task1/client/api/users/', {
          axios.put('http://192.168.0.15/~user15/REST/client/api/order/', {
          login: 'dddddd',
          pass: '123456'
        }, this.config)
        .then(function (response) {
          console.log(response);
        })
        .catch(function (error) {
          console.log(error);
        });
      },
       testDelete: function(){
          // axios.get('http://rest/user6/rest_task1/client/api/cars/1', this.config)
          axios.delete('http://192.168.0.15/~user15/REST/client/api/cars/1/', this.config)
            .then(function (response) {
            console.log(response.data);
        })
        .catch(function (error) {
          console.log(error);
        });
      }
  },
  created(){
    //this.testGet()
   //this.testPost()
    //this.testPut()
    this.testDelete()
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
