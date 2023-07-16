<template>
  <v-container fluid class="background-container">
    <v-app-bar class="background-container pt-5 pb-12" app elevation="0">
      <v-img
        class="logo"
        lazy-src="https://picsum.photos/id/11/10/6"
        max-height="70"
        max-width="150"
        src="../assets/AusleihApp.png"
      ></v-img>
      <v-spacer></v-spacer>
      <v-btn
        text
        color="white"
        :style="{ backgroundColor: '#435626' }"
        @click="overlayVisible = true"
      >
        Sign in
      </v-btn>
    </v-app-bar>

    <v-overlay v-model="overlayVisible" opacity="0.8" color="black">
      <v-card class="form-card">
        <v-card-title
          class="text-h2 text-md-h5 text-lg-h4 text-center"
          style="color: black"
        >
          Sign in
        </v-card-title>
        <v-card-text>
          <v-text-field
            v-model="username"
            :rules="nameRules"
            label="Username"
            required
            outlined
            class="custom-text-field"
          ></v-text-field>
          <v-text-field
            v-model="password"
            :rules="passwordRules"
            label="Password"
            required
            outlined
            class="custom-text-field"
            type="password"
          ></v-text-field>
        </v-card-text>
        <v-card-actions class="d-flex justify-center">
          <v-btn
            class="custom-button pl-12 pr-12 pt-40 pb-40"
            rounded
            color="primary"
            dark
            @click="resetValidation"
          >
            Login
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-overlay>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      overlayVisible: false,
      showLoginForm: false,
      name: "",
      email: "",
      password: "",
      nameRules: [(v) => !!v || "Username is required"],
      emailRules: [
        (v) => !!v || "Email is required",
        (v) => /.+@.+\..+/.test(v) || "Email must be valid",
      ],
      passwordRules: [
        (v) => !!v || "Password is required",
        (v) =>
          (v && v.length >= 8) || "Password must be at least 8 characters long",
        (v) => /\d/.test(v) || "Password must contain at least one digit",
        (v) =>
          /[a-z]/.test(v) ||
          "Password must contain at least one lowercase letter",
        (v) =>
          /[A-Z]/.test(v) ||
          "Password must contain at least one uppercase letter",
        (v) =>
          /[!@#$%^&*]/.test(v) ||
          "Password must contain at least one special character (!@#$%^&*)",
      ],
    };
  },
  methods: {
    resetValidation() {
      // Reset validation logic
    },
  },
};
</script>

<style scoped>
.background-container {
  background: linear-gradient(to right, #69e9ff, #00ff9d);
}

.form-container {
  margin-top: 60px;
}

.logo {
  position: absolute;
  top: 8px;
  left: 8px;
}

.form-card {
  padding: 160px;
  background-color: orange;
  color: black;

  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1), 0 2px 4px rgba(0, 0, 0, 0.1);
}

.custom-button {
  padding: 18px 35px;
  font-weight: bold;
}

/* Added styles for v-text-field */
::v-deep .form-card .v-text-field {
  color: black;
}

.custom-text-field .v-input__control {
  background-color: #f2f2f2;
  color: black;
}
</style>
