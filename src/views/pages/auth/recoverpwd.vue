<script>
import Auth from "../../layouts/auth";
import appConfig from "../../../../app.config";

/**
 * Recoverpwd-1 component
 */
export default {
  components: {
    Auth,
  },
   page: {
    title: "Recoverpwd-1",
    meta: [{ name: "description", content: appConfig.description }],
  },
  data() {
    return {};
  },
  layout: "auth",
};
</script>

<template>
  <Auth>
    <div class="row justify-content-center">
      <div class="col-md-8 col-lg-6 col-xl-4">
        <div class="card">
          <div class="card-body p-4">
            <div class="text-center w-75 m-auto">
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
              <p class="text-muted mb-4 mt-3">
                Enter your email address and we'll send you an email with
                instructions to reset your password.
              </p>
            </div>

            <form action="#">
              <div class="mb-3">
                <label for="emailaddress" class="form-label">Email address</label>
                <input
                  class="form-control"
                  type="email"
                  id="emailaddress"
                  required
                  placeholder="Enter your email"
                />
              </div>

              <div class="d-grid text-center">
                <button class="btn btn-primary" type="submit">
                  Reset Password
                </button>
              </div>
            </form>
          </div>
          <!-- end card-body -->
        </div>
        <!-- end card -->

        <div class="row mt-3">
          <div class="col-12 text-center">
            <p class="text-muted">
              Back to
              <router-link
                to="/auth/login-1"
                class="text-primary fw-medium ms-1"
                >Log in</router-link
              >
            </p>
          </div>
          <!-- end col -->
        </div>
        <!-- end row -->
      </div>
      <!-- end col -->
    </div>
    <!-- end row -->
  </Auth>
</template>
