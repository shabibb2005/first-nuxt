<template>
  <div class="overflow-x-hidden w-100vw">
    <div class="row auth-page">
      <div class="col-lg-6 pt-5">
        <p class="head">
          Already a member?<nuxt-link to="/signin" class="btn1">
            Sign in now</nuxt-link
          >
        </p>
        <div class="menubar mx-lg-5 mx-4">
          <h1 class="header mb-4">Sign Up</h1>
          <label for="name">Full Name</label>
          <input
            v-model="form.name"
            class="mail mb-3"
            type="name"
            name="name"
            id="name"
            placeholder="  Enter Full Name"
          />
          <label class="input1" for="email">Email Address </label>
          <input
            v-model="form.email"
            class="mail mb-3"
            type="email"
            id="mail"
            name="mail"
            placeholder="  Enter your mail"
            required
          />
          <label for="Password">Password</label>
          <input
            v-model="form.password"
            class="mail mb-3"
            type="password"
            name="password"
            id="password"
            placeholder="  Enter password"
          />
          <label for="Password">Confirm Password</label>
          <input
            v-model="form.confirm_password"
            class="mail mb-3"
            type="password"
            name="password"
            id="password"
            placeholder="  Enter confirm password"
          />
          <div class="checkbox mt-3 mb-2">
            <div>
              <input type="checkbox" id="checkbox" v-model="agree" />
              <label class="ml-2" for="checkbox"
                >I agree to the <a class="btn1">Terms </a> and
                <a class="btn1"> Privacy policy</a>
              </label>
            </div>
          </div>
          <button class="btn3" :disabled="!agree">Sign In</button>
          <div class="separetor"></div>
          <div class="choice"><p class="text">Or continue with</p></div>
          <div class="btn8 mb-4">
            <button class="btn5">
              <i class="fab fa-google mr-2"></i>Google
            </button>
            <button class="btn5">
              <i class="fab fa-facebemailook mr-2"></i>Facebook
            </button>
          </div>
        </div>
      </div>
      <div class="col-lg-6 pt-5 bg">
        <div class="logo pl-0 pl-lg-5">
          <img src="../static/logo.png" alt="logo" />
        </div>
        <p class="add">Join the largest Designer community in the world</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        name: "",
        email: "",
        password: "",
        confirm_password: "",
      },
      agree: "false",
    };
  },
};
</script>

<style scoped>
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
@media (max-width: 767px) {
  .add {
    font-size: 25px;
  }
}
</style>
