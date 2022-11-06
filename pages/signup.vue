<template>
  <div class="overflow-x-hidden w-100vw">
    <div class="row auth-page">
      <div class="col-lg-6 pt-5">
        <p class="head pr-5">
          Already a member?
          <nuxt-link to="/signin">Sign in now</nuxt-link>
        </p>
        <form class="auth-form mx-lg-5 mx-4" @submit.prevent="submit">
          <h1 class="mb-5">Sign Up</h1>

          <div class="form_group">
            <label for="name">Full Name</label>
            <input
              v-model="form.name"
              class="mb-4 px-3"
              type="text"
              id="name"
              placeholder="Enter Full Name"
              required
            />
          </div>
          <div class="form_group">
            <label class="input" for="email">Email Address </label>
            <input
              v-model="form.email"
              class="mb-4 px-3"
              type="email"
              id="email"
              placeholder="Enter your mail"
              required
            />
          </div>
          <div class="form_group">
            <label for="Password">Password</label>
            <i
              class="fas fa-eye-slash"
              v-if="show_password"
              @click="toggle_password"
            ></i>
            <i class="fas fa-eye" v-else @click="toggle_password"></i>
            <input
              v-model="form.password"
              class="mb-4 px-3"
              :type="show_password ? 'text' : 'password'"
              id="password"
              placeholder="Enter password"
              required
            />
          </div>
          <div class="form_group">
            <label for="confirm_Password">Confirm Password</label>
            <i
              class="fas fa-eye-slash"
              v-if="show_confirm_password"
              @click="toggle_confirm_password"
            ></i>
            <i class="fas fa-eye" v-else @click="toggle_confirm_password"></i>
            <input
              v-model="form.confirm_password"
              class="mb-4 px-3"
              :type="show_confirm_password ? 'text' : 'password'"
              id="confirm_password"
              placeholder="Enter confirm password"
              required
            />
          </div>

          <div class="checkbox mt-3 mb-2">
            <div>
              <input type="checkbox" id="checkbox" v-model="agree" />
              <label class="ml-2" for="checkbox">
                I agree to the <a>Terms </a> and
                <a> Privacy policy</a>
              </label>
            </div>
          </div>
          <button class="submit-btn" :disabled="!agree" type="submit">
            Submit
          </button>
          <div class="separetor"></div>
          <div class="choice mb-3"><p class="text">Or continue with</p></div>
          <div class="social-auth-btn mb-4">
            <button><i class="fab fa-google mr-2"></i>Google</button>
            <button><i class="fab fa-facebook mr-2"></i>Facebook</button>
          </div>
        </form>
      </div>
      <div class="col-lg-6 pt-5 bg">
        <div class="logo pl-0 pl-lg-5">
          <img src="../static/logo.png" alt="logo" />
        </div>
        show_confirm_password
        <p class="auth-dialog">
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
      form: {
        name: "",
        email: "",
        password: "",
        confirm_password: "",
      },
      agree: false,
      show_password: false,
      show_confirm_password: false,
    };
  },

  methods: {
    submit() {
      console.log(this.form);
    },

    toggle_password() {
      this.show_password = !this.show_password;
    },

    toggle_confirm_password() {
      this.show_confirm_password = !this.show_confirm_password;
    },
  },
};
</script>

<style scoped>
.social-auth-btn.mb-4 {
  display: flex;
  justify-content: space-between;
  grid-gap: 20px;
}

button {
  flex: 1;
  height: 50px;
  font-size: 19px;
  border: 1px solid #ddd;
}
button.submit-btn {
  display: block;
  width: 100%;
  height: 60px;
  border-radius: 4px;
  background: #242020;
  color: white;
  font-size: 20px;
}
.form_group i {
  position: absolute;
  right: 20px;
  bottom: 20px;
  cursor: pointer;
}

.form_group {
  position: relative;
}
.form_group label {
  font-size: 20px;
}
.head {
  text-align: right;
}
.form_group input {
  display: block;
  height: 60px;
  width: 100%;
  border-radius: 5px;
  font-size: 18px;
  border: 1px solid #ddd;
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
.choice p {
  color: #898080;
  background: white;
  padding: 0 20px;
}
.auth-dialog {
  font-weight: 300;
  font-size: 65px;
  padding: 100px 45px;
}

@media (min-width: 992px) and (max-width: 1200px) {
  .auth-dialog {
    font-size: 50px;
    padding: 85px 32px;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .bg {
    height: auto;
    padding: 40px 0;
  }
  .auth-dialog {
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
  .auth-dialog {
    font-size: 20px;
    padding: 0px 24px;
    text-align: center;
  }
  .auth-page {
    min-height: auto;
  }
}
@media (max-width: 410px) {
  .checkbox {
    flex-direction: column;
  }
}
@media (max-width: 767px) {
  .auth-dialog {
    font-size: 25px;
  }
}
/* .form_group i {
  position: absolute;
  bottom: 20px;
  right: 25px;
  cursor: pointer;
}

.form_group {
  position: relative;
} */
.form_group i {
  position: absolute;
  right: 20px;
  bottom: 20px;
  cursor: pointer;
}

.form_group {
  position: relative;
}
</style>
