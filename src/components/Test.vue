<template>
    <div id="Test">
        <h1>{{msg}} - {{user.firstName}}</h1>    
        <br>
        <hr>
        <br>
        <div v-if="showName" v-html="myHtml"></div>
        <div v-else>
            Var showName is {{showName}}
        </div>
        <br>
        <hr>
        <br>
        <ul>
          <li v-for="task in tasks" :key="task.title">
            {{task.title}}
          </li>
        </ul>
        <br>
        <hr>
        <br>
        <input type="text" v-model="user.firstName">
        <button v-on:click="saludar(user.firstName)">Saludar</button>
        <br>
        <hr>
        <br>
        <input type="text" v-on:keyup.enter="typingEnter">
        <br>
        <hr>
        <br>
        <h1>Nombre completo: {{fullName}}</h1>  
    </div>
</template>

<script>
export default {
    data() {
        return {
            title: 'Text',
            user: {
                firstName: 'Cesar',
                lastName: 'Nuñez'
            },
            myHtml: '<h3>Hola myHtml</h3>',
            showName: true,
            tasks: [
              {title: 'eat'},
              {title: 'sleep'},
              {title: 'play'}
            ]
        }
    },
    methods: {
      saludar(userName) {
        alert('hello '+userName)
      },
      typingEnter (e) {
        //console.log(e.target.value);
        console.log('Precionaste la tecla [Enter]');
      }
    },
    computed: {
      fullName() {
        return this.user.firstName+' '+this.user.lastName;
      }
    },
    props: {
      msg: {
        type: String
      }
    }
}
</script>

<style scoped>

</style>