<template>
  <form>
    <div class="home">
      <v-row>
        <v-col cols="12" md="6">
          <v-text-field
            v-model="state.customer"
            name="customer"
            :error-messages="v$.customer.$errors.map((e) => e.$message)"
            label="Customer Name"
            required
            @input="v$.customer.$touch"
            @blur="v$.customer.$touch"
            variant="outlined"
            color="#013220"
          ></v-text-field>
        </v-col>

        <v-col cols="12" md="6">
          <v-text-field
            v-model="state.carrier_name"
            name="carrier_name"
            :error-messages="v$.carrier_name.$errors.map((e) => e.$message)"
            label="Carrier Name"
            required
            @input="v$.carrier_name.$touch"
            @blur="v$.carrier_name.$touch"
            variant="outlined"
            color="#013220"
          ></v-text-field>
        </v-col>
      </v-row>

      <v-row>
        <v-col cols="2" md="3">
          <h3>Transporation mode</h3>
        </v-col>

        <v-col cols="8" md="3">
          <input
            class="form-check-input"
            type="radio"
            name="flexRadioDefault"
            id="flexRadioDefault1"
            v-model="state.selectMode"
            value="IML"
          />
          <label class="form-check-label" for="flexRadioDefault1"> IML </label>
        </v-col>

        <v-col cols="8" md="3">
          <input
            class="form-check-input"
            type="radio"
            name="flexRadioDefault"
            id="flexRadioDefault2"
            v-model="state.selectMode"
            value="HWY"
          />
          <label class="form-check-label" for="flexRadioDefault1"> HWY </label>
        </v-col>

        <v-col cols="8" md="3">
          <input
            class="form-check-input"
            type="radio"
            name="flexRadioDefault"
            id="flexRadioDefault3"
            v-model="state.selectMode"
            value="LTL"
          />
          <label class="form-check-label" for="flexRadioDefault1"> LTL </label>
        </v-col>
      </v-row>
      <br />
      <v-row>
        <v-col cols="8" md="3">
          <v-text-field
            v-model="state.origin_name"
            name="origin_name"
            :error-messages="v$.origin_name.$errors.map((e) => e.$message)"
            label="Origin Name"
            required
            @input="v$.origin_name.$touch"
            @blur="v$.origin_name.$touch"
            variant="outlined"
            color="#013220"
          ></v-text-field>
        </v-col>

        <v-col cols="8" md="3">
          <v-text-field
            v-model="state.origin_city"
            name="origin_city"
            :error-messages="v$.origin_city.$errors.map((e) => e.$message)"
            label="Origin City"
            required
            @input="v$.origin_city.$touch"
            @blur="v$.origin_city.$touch"
            variant="outlined"
            color="#013220"
          ></v-text-field>
        </v-col>

        <v-col cols="8" md="3">
          <v-text-field
            v-model="state.origin_state"
            name="origin_state"
            :error-messages="v$.origin_state.$errors.map((e) => e.$message)"
            label="Origin State"
            required
            @input="v$.origin_state.$touch"
            @blur="v$.origin_state.$touch"
            variant="outlined"
            color="#013220"
          ></v-text-field>
        </v-col>

        <v-col cols="8" md="3">
          <v-text-field
            v-model="state.origin_zipCode"
            name="origin_zipCode"
            :error-messages="v$.origin_zipCode.$errors.map((e) => e.$message)"
            label="Origin ZipCode"
            required
            @input="v$.origin_zipCode.$touch"
            @blur="v$.origin_zipCode.$touch"
            variant="outlined"
            color="#013220"
            type="number"
          ></v-text-field>
        </v-col>
      </v-row>

      <v-row>
        <v-col cols="12" md="3">
          <v-text-field
            v-model="state.destination_name"
            name="destination_name"
            :error-messages="v$.destination_name.$errors.map((e) => e.$message)"
            label="Destination Name"
            required
            @input="v$.destination_name.$touch"
            @blur="v$.destination_name.$touch"
            variant="outlined"
            color="#013220"
          ></v-text-field>
        </v-col>

        <v-col cols="12" md="3">
          <v-text-field
            v-model="state.destination_city"
            name="destination_city"
            :error-messages="v$.destination_city.$errors.map((e) => e.$message)"
            label="Destination City"
            required
            @input="v$.destination_city.$touch"
            @blur="v$.destination_city.$touch"
            variant="outlined"
            color="#013220"
          ></v-text-field>
        </v-col>

        <v-col cols="12" md="3">
          <v-text-field
            v-model="state.destination_state"
            name="destination_state"
            :error-messages="
              v$.destination_state.$errors.map((e) => e.$message)
            "
            label="Destination State"
            required
            @input="v$.destination_state.$touch"
            @blur="v$.destination_state.$touch"
            variant="outlined"
            color="#013220"
          ></v-text-field>
        </v-col>

        <v-col cols="12" md="3">
          <v-text-field
            v-model="state.destination_zip_code"
            name="destination_zip_code"
            :error-messages="
              v$.destination_zip_code.$errors.map((e) => e.$message)
            "
            label="Destination ZipCode"
            required
            @input="v$.destination_zip_code.$touch"
            @blur="v$.destination_zip_code.$touch"
            variant="outlined"
            color="#013220"
            type="number"
          ></v-text-field>
        </v-col>
      </v-row>

      <v-row>
        <v-col cols="12" md="4">
          <v-text-field
            v-model="state.total_pieces"
            name="total_pieces"
            :error-messages="v$.total_pieces.$errors.map((e) => e.$message)"
            label="Total Pieces"
            required
            @input="v$.total_pieces.$touch"
            @blur="v$.total_pieces.$touch"
            variant="outlined"
            color="#013220"
            type="number"
          ></v-text-field>
        </v-col>

        <v-col cols="12" md="4">
          <v-text-field
            v-model="state.total_weight"
            name="total_weight"
            :error-messages="v$.total_weight.$errors.map((e) => e.$message)"
            label="Total Weight"
            required
            @input="v$.total_weight.$touch"
            @blur="v$.total_weight.$touch"
            variant="outlined"
            color="#013220"
            type="number"
          ></v-text-field>
        </v-col>

        <v-col cols="12" md="4">
          <v-text-field
            v-model="state.commodity_description"
            name="commodity_description"
            :error-messages="
              v$.commodity_description.$errors.map((e) => e.$message)
            "
            label="Commodity Description"
            required
            @input="v$.commodity_description.$touch"
            @blur="v$.commodity_description.$touch"
            variant="outlined"
            color="#013220"
          ></v-text-field>
        </v-col>
      </v-row>
    </div>

    <div class="loader" v-if="state.loading">
      <b-spinner label="Loading..."></b-spinner>
    </div>

    <div class="button-container">
      <v-btn
        class="me-4"
        @click="validateForm"
        style="background-color: #013220; color: #ffffff"
        >Submit</v-btn
      >
      <v-btn
        class="custom-button"
        style="background-color: #013220; color: #ffffff"
        @click="clear"
      >
        clear
      </v-btn>
    </div>
  </form>
</template>
<script setup>
import { reactive } from "vue";
import { useVuelidate } from "@vuelidate/core";
import { email, required } from "@vuelidate/validators";
import axios from "axios";
import { useRouter } from "vue-router";

const router = useRouter();

const initialState = {
  customer: "",
  carrier_name: "",
  origin_name: "",
  origin_state: "",
  origin_city: "",
  origin_zipCode: "",
  // service_provider_name: "",
  destination_city: "",
  destination_name: "",
  destination_state: "",
  destination_zip_code: "",
  total_pieces: "",
  total_weight: "",
  commodity_description: "",
  selectMode: "IML",
};

const state = reactive({
  ...initialState,
  loading: false,
});

const rules = {
  customer: { required },
  carrier_name: { required },
  origin_name: { required },
  origin_city: { required },
  origin_state: { required },
  origin_zipCode: { required },
  destination_city: { required },
  destination_name: { required },
  destination_state: { required },
  destination_zip_code: { required },
  total_pieces: { required },
  total_weight: { required },
  commodity_description: { required },
};

const v$ = useVuelidate(rules, state);

function clear() {
  v$.value.$reset();

  for (const [key, value] of Object.entries(initialState)) {
    state[key] = value;
  }
}

function validateForm() {
        router.push({ name: "Prediction" });

  // v$.value.$touch();

  // if (v$.value.$error) {
  //   console.log("Validation failed");
  //   return;
  // }

  console.log("Validation passed");
  state.loading = true;

  // const formData = {
  //   customer: state.customer,
  //   carrier_name: state.carrier_name,
  //   transporation_mode: state.selectMode,
  //   origin_name: state.origin_name,
  //   origin_city: state.origin_city,
  //   origin_state: state.origin_state,
  //   origin_zipCode: state.origin_zipCode,
  //   destination_name: state.destination_name,
  //   destination_city: state.destination_city,
  //   destination_state: state.destination_state,
  //   destination_zip_code: state.destination_zip_code,
  //   total_pieces: state.total_pieces,
  //   total_weight: state.total_weight,
  //   commodity_description: state.commodity_description,
  // };

  // axios
  //   .post("http://127.0.0.1:5000/api/theft/submit", formData)
  //   .then((response) => {
  //     state.loading = false;
  //     router.push({ name: "Prediction" });
  //   })
  //   .catch((error) => {
  //     console.error("Error:", error);
  //   });

  // console.log(state.selectMode);
}
</script>

<style>
@import "../css/Home.css";
</style>
