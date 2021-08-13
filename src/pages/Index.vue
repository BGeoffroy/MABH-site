<style>
body {font-family: Arial, Helvetica, sans-serif;}
form {border: 3px solid #f1f1f1;}

input[type=text], input[type=password] {
  width: 100%;
  padding: 12px 20px;
  margin: 8px 0;
  display: inline-block;
  border: 1px solid #ccc;
  box-sizing: border-box;
}

button {
  background-color: #04AA6D;
  color: white;
  padding: 14px 20px;
  margin: 8px 0;
  border: none;
  cursor: pointer;
  width: 100%;
}

button:hover {
  opacity: 0.8;
}

.cancelbtn {
  width: auto;
  padding: 10px 18px;
  background-color: #f44336;
}

.imgcontainer {
  text-align: center;
  margin: 24px 0 12px 0;
}

img.avatar {
  width: 40%;
  border-radius: 50%;
}

.container {
  padding: 16px;
}

span.psw {
  float: right;
  padding-top: 16px;
}

/* Change styles for span and cancel button on extra small screens */
@media screen and (max-width: 300px) {
  span.psw {
     display: block;
     float: none;
  }
  .cancelbtn {
     width: 100%;
  }
}
</style>


<script src = "https://cdn.jsdelivr.net/npm/vue@2.6.14/dist/vue.js"></script>
<template>
  <Layout>
  <div class="imgcontainer">
    <img src="img_avatar2.png" alt="Avatar" class="avatar">
  </div>
    <label for="un">Username</label>
    <input id="un" type="text" placeholder="Enter Username" v-model="username" />
    
    <label for="pw">Password</label>
    <input id="pw" type="password" placeholder="Enter Password" v-model="password" />
    <button type="submit" v-on:click="submit">Login</button>
    <label>
      <input type="checkbox" checked="checked" name="remember"> Remember me
    </label>
    <label>{{username}}</label>
    <button type="button" class="cancelbtn">Cancel</button>

  </Layout>
</template>

<script>
    const app = new Vue({
        el: '#app',
        data: {
            username: '',
            password: '',
            shoppingCart: [
                { label: 'Apples', cost: 6 },
                { label: 'Bananas', cost: 2 },
                { label: 'Coconuts', cost: 8 }
            ]
        },
        
        computed: {
        },
        methods: {
            submit() {
                alert("You submitted Username:" + this.username + " and Password:" + this.password)
                console.log("sending")
                socket.emit("authorization", this.username)
                console.log("sent!")
            }
        }

    })
</script>




