
<template>
<nav>

<v-app>
    <!-- <v-app-bar app dark color="blue">
      <v-toolbar-title>vue</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn text rounded>Home</v-btn>
      <v-btn text rounded>Login</v-btn>
      <v-btn text rounded>About</v-btn>
      <v-btn text rounded>Contact Us</v-btn>
    
   </v-app-bar> -->
   
   <v-content>
    <v-card width="500" class="mx-auto mt-9">
      <v-card-title >Login Page</v-card-title>
      <v-card-text>
        <v-text-field label="username" prepend-icon="mdi-account-circle" v-model="username" :rules="inputRules"/>
        <v-text-field label="password" 
        :type=" showPassword ? 'text' : 'password'"
        prepend-icon="mdi-lock"
       :append-icon=" showPassword ? 'mdi-eye' : 'mdi-eye-off'"
       @click:append="showPassword = !showPassword" v-model="password" :rules="inputRules1"/>
      </v-card-text>

      <v-divider></v-divider>
        <v-card-actions>
          <v-btn color="success">Register</v-btn>
          <v-btn color="info"  @click="login" v-model="login">Login</v-btn>

        </v-card-actions>
      
    </v-card>
   </v-content>
</v-app>
</nav>

</template>
<script>
import Toolbar from '@/components/ToolBar.vue'


export default {
  name:'App',
  components:{Toolbar},

  data(){
    

    return{
      // showPassword:false
      username:'',
      password:'',
     inputRules:[
        v => v.length>=5 || 'Please Enter Username'
      ],
      inputRules1:[
        v1 => v1.length>=3 || 'Please Enter Password'
      ],
      


    

    }
  },methods:{
    login(){
      console.log(this.username,this.password)
    }
  }
  
}
</script>