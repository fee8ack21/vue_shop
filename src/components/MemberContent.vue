<template>
  <main class="main-member">
    <div class="container d-flex justify-content-center align-items-center py-5">
      <!-- login -->
      <form action="" class="member-form rounded p-3" v-if="formState === 1">
        <h2 class="form-title text-center mb-4">LOG IN</h2>
        <div class="form-group">
          <label for="loginAccount">Account </label>
          <input type="text" class="form-control" id="loginAccount" />
        </div>
        <div class="form-group">
          <label for="loginPassword">Password </label>
          <input type="password" class="form-control" id="loginPassword" />
        </div>
        <div class="form-group mb-4">
          <a href="#" class="text-danger" @click.prevent="formState = 3">
            <small>Forgot your password ?</small>
          </a>
        </div>
        <div class="button-wrap d-flex justify-content-center">
          <button type="button" class="btn btn-secondary mx-2" @click="formState = 2">
            Sign Up
          </button>
          <button type="button" class="btn btn-primary mx-2">Log In</button>
        </div>
      </form>
      <!-- signup -->
      <form action="" class="member-form rounded p-3" v-if="formState === 2">
        <h2 class="form-title text-center mb-4">SIGN UP</h2>
        <div class="form-group">
          <label for="signupAccount">Account </label>
          <input type="text" class="form-control" id="signupAccount" />
        </div>
        <div class="form-group">
          <label for="signupPassword">Password </label>
          <input type="password" class="form-control" id="signupPassword" />
        </div>
        <div class="form-group">
          <label for="signupEmail">Email </label>
          <input type="email" class="form-control" id="signupEmail" />
        </div>
        <div class="form-group mb-4 d-flex align-items-center">
          <input type="checkbox" id="signupSubscribe" class="mr-2" />
          <label for="signupSubscribe" class="mb-0">
            <small>Subscribe our newsletter </small>
          </label>
        </div>
        <div class="button-wrap d-flex justify-content-center">
          <button type="button" class="btn btn-secondary mx-2" @click="formState = 1">
            Log In
          </button>
          <button type="button" class="btn btn-primary mx-2">Sign Up</button>
        </div>
      </form>
      <!-- reset -->
      <form action="" class="member-form rounded p-3" v-if="formState === 3">
        <h2 class="form-title text-center mb-4">RESET</h2>
        <div class="form-group mb-4">
          <label for="resetEmail">Email </label>
          <input type="email" class="form-control" id="resetEmail" />
        </div>
        <div class="button-wrap d-flex justify-content-center">
          <button type="button" class="btn btn-secondary mx-2" @click="formState = 2">
            Back
          </button>
          <button type="button" class="btn btn-primary mx-2">Send</button>
        </div>
      </form>
    </div>
  </main>
</template>

<script>
export default {
  name: 'MemberContent',
  data() {
    return {
      formState: 1,
    };
  },
};
</script>

<style lang="scss">
.main-member {
  min-height: calc(100vh - 152px);
  & > div {
    min-height: calc(100vh - 152px);
  }
  .member-form {
    width: 500px;
    border: 1px solid #ced4da;
    .form-title,
    label {
      user-select: none;
    }
    input {
      background-color: transparent;
      transition: 0.15s;
    }
    .button-wrap {
      button {
        width: 100px;
      }
    }
  }
}
</style>
