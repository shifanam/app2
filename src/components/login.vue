<template>
<div class="login">
  <div class="row">
    <div class="col-xs-12">
      <ul class=nave-bar>
      </ul>
    </div>
  </div>
  <div class="log">
    <div class="row">
      <div class="col-xs-6 col-sm-6 col-lg-6 col-md-6">
        <div class="row">
          <div class="col-xs-12 col-sm-12 col-lg-12 col-md-12">
            <img  src="../assets/login2.jpg" height="110px" width="100px">
          </div>
        </div>
        <div class="row">
          <div class="col-xs-12 col-sm-12 col-lg-12 col-md-12">
            <label for="email">Enter Your Email</label>
            <input type="email" name="email" placeholder="" id="email" value="" required v-model="email">
          </div>
        </div>
        <br>
        <div class="row">
          <div class="col-xs-12 col-sm-12 col-lg-12 col-md-12">
            <label for="password">Enter Your Password</label>
            <input type="password" name="password" placeholder="" id="password" value="" required v-model="password">
          </div>
        </div>
        <br>
        <div class="row">
          <div class="col-xs-12 col-sm-12 col-lg-12 col-md-12">
            <div class="btn-medium" v-on:click="logins()">LOGIN</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>
</template>
<script>
export default {
  data () {
    return {
      password: '',
      email: ''
    }
  },
  methods: {
    logins: function () {
      let logEmail = this.email
      let logPass = this.password
      let stEmail = this.$localStorage.get('email')
      let stPass = this.$localStorage.get('pass')
      if (logEmail === stEmail && logPass === stPass) {
        alert('login sucessfully')
        this.$router.push({path: '/dashboard'})
      } else {
        alert('Invalid email or password')
        return false
      }
    }
  }
}
</script>
<style>
body {
  background-image: url("");
  background-repeat: no-repeat;
  background-color: #fff;
  margin-top: -1%;
  margin-left: -1%;
  width:100%;
  margin-bottom: 0;
  background-attachment: fixed;
  -webkit-background-size: cover;
  -moz-background-size: cover;
  background-size: cover;
}

.nave-bar {
  background-color:none;
  display: block;
  height: 50px;
  width: 100%;
  text-decoration: none;
}

ul, li {
  list-style-type: none;
  display: block;
  overflow: hidden;
  margin: 0;
  padding-left: 12px;
  padding-top: 18px;
  float: left;
  top: 0;
  color: #fff;
  cursor: pointer;
}

a {
    text-decoration: none;
}

label {
  position: relative;
  left: 2px;
  color: #000;
  font-size: 1em;
}

input, text {
  font-size: 1em;
  display: block;
  width: 93%;
  padding:1em 1em 1em 0;
  background: none;
  background-image: none;
  border: none;
  border-bottom: 1px solid #8e8e8e;
  color: #000;
  border-radius: 0;
  -webkit-transition: border-color .25s ease, box-shadow .25s ease;
  -moz-transition: border-color .25s ease, box-shadow .25s ease;
  transition: border-color .25s ease, box-shadow .25s ease;
}

.log {
  width:20%;
  height:100%;
  border: #000;
  border:0px solid #000;
  background-image: url("");
  border-radius: .1em;
  padding-right: 5%;
  padding-top: 3%;
  padding-left: 5%;
  padding-bottom: 3%;
  float: right;
  color: #000;
  margin-right: 5%;
  font: 1em sans-serif;
  border-radius: 1em;
  margin-right: 5%;
  box-shadow: 0 4px 20px 0 rgba(0,0,0,0.2);
}

.log:hover {
  box-shadow: 0 8px 22px 0 rgba(0,0,0,0.2);
}

label {
  float: left;
}

.btn-medium {
  background-color:#2196f3;
  font-size: 14px;
  font-family: 'Roboto';
  text-align :center;
  color: white;
  width:90px;
  padding:10px;
  cursor: pointer;
  border-radius: 0.3em;
  text-decoration: none;
  box-shadow: 0 4px 2px 0 rgba(0.1,0.1,0.1,0.2);
}

.btn-medium:hover, .btn-medium:focus {
  background: #2196f3;
  letter-spacing: 7px;
  box-shadow: 2px 2px 2px 2px rgba(1,0,0,0.1);
}

.btn-medium {
  display: block;
  width: 92%;
}

</style>
