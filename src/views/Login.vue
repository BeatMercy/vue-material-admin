<template>
  <v-app class="split-bg primary">
    <v-content>
      <v-container
        fluid
        fill-height
      >
        <v-layout
          align-center
          justify-center
        >
          <v-flex
            xs12
            sm8
            md4
            lg4
          >
            <v-card class="elevation-1 pa-3">
              <v-card-text>
                <div class="layout column align-center">
                  <img
                    src="../assets/logo.jpg"
                    alt="大叶榕供应链科技（深圳）有限公司"
                    width="120"
                    height="120"
                  >
                  <h4 class="flex my-4 ">
                    <b>大叶榕供应链科技（深圳）有限公司</b>
                  </h4>
                </div>
                <v-form>
                  <v-text-field
                    v-model="model.username"
                    append-icon="person"
                    name="login"
                    label="Login"
                    type="text"
                  />
                  <v-text-field
                    id="password"
                    v-model="model.password"
                    append-icon="lock"
                    name="password"
                    label="Password"
                    type="password"
                  />
                </v-form>
              </v-card-text>
              <div class="login-btn">
                <v-btn icon>
                  <v-icon color="blue">
                    fa fa-facebook-square fa-lg
                  </v-icon>
                </v-btn>
                <v-btn icon>
                  <v-icon color="red">
                    fa fa-google fa-lg
                  </v-icon>
                </v-btn>
                <v-btn icon>
                  <v-icon color="light-blue">
                    fa fa-twitter fa-lg
                  </v-icon>
                </v-btn>
                <v-spacer />
                <v-btn
                  block
                  color="primary"
                  :loading="loading"
                  @click="login"
                >
                  Login
                </v-btn>
              </div>
            </v-card>
          </v-flex>
        </v-layout>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
export default {
  data: () => ({
    loading: false,
    model: {
      username: '乐珈彤',
      password: '123456'
    }
  }),

  methods: {
    login () {
      this.loading = true
      setTimeout(() => {
        this.$router.push('/dashboard')
      }, 1000)
    }
  }
}
</script>
<style scoped lang="css">
.split-bg {
  height: 50%;
  width: 100%;
  position: absolute;
  top: 0;
  left: 0;
  content: "";
  z-index: 0;
}
</style>
