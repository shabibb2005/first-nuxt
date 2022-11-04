<template>
  <div class="overflow-x-hidden w-100vw">
    <div class="row auth-page">
      <div class="col-lg-6 pt-5">
        <p class="head">
          Not A Member?
          <nuxt-link :to="{ name: 'signup' }" class="btn1"
            >Sign up now</nuxt-link
          >
        </p>
        <div class="menubar mx-lg-5 mx-4">
          <h1 class="header mb-5">Sign In</h1>
          <label for="email">Email Address </label>
          <br />
          <input
            v-model="Form.email"
            class="mail mb-3"
            type="email"
            id="mail"
            name="mail"
            placeholder="  Enter your mail"
            required
          /><br />
          <label for="Password">Password</label>
          <br />
          <input
            v-model="Form.password"
            class="mail mb-3"
            type="password"
            name="password"
            id="password"
            placeholder="  Enter your password"
          />
          <br />
          <div class="checkbox">
            <div>
              <input type="checkbox" id="checkbox" v-model="agree" />
              <label class="ml-2" for="checkbox">Remember Me</label>
            </div>
            <a class="btn1">Forget Password</a>
          </div>
          <br />
          <button class="btn3" :disabled="!agree">Sign In</button>
          <div class="separetor"></div>
          <div class="choice"><p class="text">Or continue with</p></div>
          <br />
          <div class="btn8 mb-3 mb-lg-0">
            <button class="btn5">
              <i class="fab fa-google mr-2"></i>Google
            </button>
            <button class="btn5">
              <i class="fab fa-facebook mr-2"></i>Facebook
            </button>
          </div>
        </div>
      </div>
      <div class="col-lg-6 pt-lg-5 bg">
        <div class="logo pl-0 pl-lg-5">
          <img src="../static/logo.png" alt="logo" />
          <br />
        </div>
        <p class="add mb-0 mt-2 mt-lg-1">
          Join the largest Designer community in the world
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      Form: {
        email: "",
        password: "",
      },
      agree: "false",
    };
  },
};
</script>

<style>
* {
  font-family: "Poppins", sans-serif;
}
.bg {
  background: #ddd;
}
.w-100vw {
  width: 100vw;
}
.overflow-x-hidden {
  overflow-x: hidden;
}
.auth-page {
  min-height: 100vh;
}
.head {
  text-align: right;
  margin-right: 65px;
}
label {
  font-size: 19px;
}
.mail {
  height: 60px;
  width: 100%;
  border-radius: 4px;
  font-size: 18px;
  border: none;
  background: #eff2f5;
}
button.btn3 {
  height: 65px;
  width: 100%;
  background: #201f1f;
  color: white;
  border-radius: 4px;
  font-size: 20px;
}
.logo {
  display: flex;
  justify-content: flex-start;
}
.checkbox {
  display: flex;
  justify-content: space-between;
}
.separetor {
  height: 2px;
  width: 100%;
  background-color: #ddd;
  margin-top: 50px;
}
.choice {
  display: flex;
  justify-content: center;
  margin-top: -14px;
}
.text {
  color: #898080;
  background: white;
  padding: 0 20px;
}
.btn8 {
  display: flex;
  justify-content: space-between;
  grid-gap: 20px;
  height: 50px;
}
.btn5 {
  flex: 1;
  border: 2px solid #ddd4d4;
  border-radius: 3px;
}
.header {
  font-weight: 300;
}
.add {
  font-weight: 300;
  font-size: 65px;
  padding: 100px 45px;
}
a.btn1:hover {
  cursor: pointer;
}
/*Mobile View*/
@media (min-width: 992px) and (max-width: 1200px) {
  .add {
    font-size: 50px;
    padding: 85px 32px;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .bg {
    height: auto;
    padding: 40px 0;
  }
  .add {
    font-size: 29px;
    padding: 0px 32px;
    text-align: center;
  }
  .row.auth-page {
    flex-direction: column-reverse;
  }
  .logo {
    justify-content: center;
  }
  .auth-page {
    min-height: auto;
  }
}
@media (max-width: 767px) {
  .bg {
    height: auto;
    padding: 15px 0;
  }
  .logo {
    justify-content: center;
  }
  .row.auth-page {
    flex-direction: column-reverse;
  }
  .add {
    font-size: 20px;
    padding: 0px 24px;
    text-align: center;
  }
  .auth-page {
    min-height: auto;
  }
  .btn1 {
    font-size: 18px;
  }
  .head {
    text-align: right;
    margin-right: 25px;
  }
}
@media (max-width: 410px) {
  .checkbox {
    flex-direction: column;
  }
}
</style>
