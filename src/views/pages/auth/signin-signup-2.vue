<script>
import Auth from "../../layouts/auth-2";
import appConfig from "../../../../app.config";

/**
 * Signin signup-2 component
 */
export default {
  page: {
    title: "Signin signup-2",
    meta: [{ name: "description", content: appConfig.description }],
  },
  data() {
    return {};
  },
  components: {
    Auth,
  },
};
</script>

<template>
  <Auth>
    <!-- Logo -->
    <div class="auth-brand text-center text-lg-left">
      <div class="auth-logo">
        <router-link to="/" class="logo logo-dark text-center">
          <span class="logo-lg">
            <img src="@/assets/images/logo-dark.png" alt height="22" />
          </span>
        </router-link>
        <router-link to="/" class="logo logo-light text-center">
          <span class="logo-lg">
            <img src="@/assets/images/logo-light.png" alt height="22" />
          </span>
        </router-link>
      </div>
    </div>
    <b-tabs nav-class="nav-tabs nav-bordered">
      <b-tab title="Log In" active>
        <p class="text-muted mb-3">
          Enter your email address and password to access admin panel.
        </p>

        <!-- form -->
        <form action="#">
          <div class="mb-2">
            <label for="emailaddress" class="form-label">Email address</label>
            <input
              class="form-control"
              type="email"
              id="emailaddress"
              required
              placeholder="Enter your email"
            />
          </div>
          <div class="mb-2">
            <router-link to="/auth/recoverpwd-2" class="text-muted float-end">
              <small>Forgot your password?</small>
            </router-link>
            <label for="password" class="form-label">Password</label>
            <input
              class="form-control"
              type="password"
              required
              id="password"
              placeholder="Enter your password"
            />
          </div>
          <div class="mb-3">
            <div class="form-check">
              <input
                class="form-check-input"
                type="checkbox"
                id="checkbox-signin"
              />
              <label class="form-check-label" for="checkbox-signin">
                Remember me
              </label>
            </div>
          </div>
          <div class="text-center d-grid">
            <button class="btn btn-primary" type="submit">Log In</button>
          </div>
          <!-- social-->
          <div class="text-center mt-4">
            <h5 class="mt-3 text-muted">Sign in with</h5>
            <ul class="social-list list-inline mt-3">
              <li class="list-inline-item">
                <a
                  href="javascript: void(0);"
                  class="social-list-item border-purple text-purple"
                >
                  <i class="mdi mdi-facebook"></i>
                </a>
              </li>
              <li class="list-inline-item">
                <a
                  href="javascript: void(0);"
                  class="social-list-item border-danger text-danger"
                >
                  <i class="mdi mdi-google"></i>
                </a>
              </li>
              <li class="list-inline-item">
                <a
                  href="javascript: void(0);"
                  class="social-list-item border-info text-info"
                >
                  <i class="mdi mdi-twitter"></i>
                </a>
              </li>
              <li class="list-inline-item">
                <a
                  href="javascript: void(0);"
                  class="social-list-item border-secondary text-secondary"
                >
                  <i class="mdi mdi-github"></i>
                </a>
              </li>
            </ul>
          </div>
        </form>
        <!-- end form-->
      </b-tab>
      <b-tab title="Sign In">
        <p class="text-muted mb-3">
          Don't have an account? Create your own account, it takes less than a
          minute
        </p>

        <!-- form -->
        <form action="#">
          <div class="mb-2">
            <label for="fullname" class="form-label">Full Name</label>
            <input
              class="form-control"
              type="text"
              id="fullname"
              placeholder="Enter your name"
              required
            />
          </div>
          <div class="mb-2">
            <label for="emailaddress1" class="form-label">Email address</label>
            <input
              class="form-control"
              type="email"
              id="emailaddress1"
              required
              placeholder="Enter your email"
            />
          </div>
          <div class="mb-2">
            <label for="password2" class="form-label">Password</label>
            <input
              class="form-control"
              type="password"
              required
              id="password2"
              placeholder="Enter your password"
            />
          </div>
          <div class="mb-3">
            <div class="form-check">
              <input
                class="form-check-input"
                type="checkbox"
                id="checkbox-signup"
              />
              <label class="form-check-label" for="checkbox-signup">
                I accept
                <a href="javascript: void(0);" class="text-dark"
                  >Terms and Conditions</a
                >
              </label>
            </div>
          </div>
          <div class="text-center d-grid">
            <button class="btn btn-primary" type="submit">Sign Up</button>
          </div>
          <!-- social-->
          <div class="text-center mt-4">
            <h5 class="mt-3 text-muted">Sign Up using</h5>
            <ul class="social-list list-inline mt-3 mb-0">
              <li class="list-inline-item">
                <a
                  href="javascript: void(0);"
                  class="social-list-item border-purple text-purple"
                >
                  <i class="mdi mdi-facebook"></i>
                </a>
              </li>
              <li class="list-inline-item">
                <a
                  href="javascript: void(0);"
                  class="social-list-item border-danger text-danger"
                >
                  <i class="mdi mdi-google"></i>
                </a>
              </li>
              <li class="list-inline-item">
                <a
                  href="javascript: void(0);"
                  class="social-list-item border-info text-info"
                >
                  <i class="mdi mdi-twitter"></i>
                </a>
              </li>
              <li class="list-inline-item">
                <a
                  href="javascript: void(0);"
                  class="social-list-item border-secondary text-secondary"
                >
                  <i class="mdi mdi-github"></i>
                </a>
              </li>
            </ul>
          </div>
        </form>
        <!-- end form-->
      </b-tab>
    </b-tabs>
    <!-- Footer-->
    <footer class="footer footer-alt">
      <p class="text-muted">
        {{ new Date().getFullYear() }}&copy; Minton theme by
        <a href="javascript: void(0);" class="text-dark">Themesbrand</a>
      </p>
    </footer>
  </Auth>
</template>
