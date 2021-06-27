<template>
  <b-container fluid class="scollbar">
    <b-row>
      <b-col class="first-column">
        <b-input
          v-model="input"
          type="number"
          pattern="[0-9]*"
          min="1"
          @keyup="filterInput()"
        ></b-input>
      </b-col>
      <b-col>
        <b-form-select v-model="selected" @change="selectMethod()" class="mb-3">
          <b-form-select-option :value="null"> Select </b-form-select-option>
          <b-form-select-option :value="true"> isPrime </b-form-select-option>
          <b-form-select-option :value="false">
            isFibanacci
          </b-form-select-option>
        </b-form-select>
      </b-col>
      <b-col class="last-column">
        {{ result }}
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      input: "",
      selected: null,
      result: "",
    };
  },
  created() {
    this.result = "";
  },
  methods: {
    filterInput() {
      this.input = parseFloat(this.input);
    },
    selectMethod() {
      console.log("selectMethod");
      console.log(this.selected);
      this.input = Math.round(this.input);
      if (this.input < 0) {
        this.input *= -1;
      }
      this.selected ? this.checkIsPrime() : this.checkIsFibanacci();
    },
    checkIsPrime() {
      console.log("checkIsPrime");
      let isPrime = true;
      if (this.input === 1) {
        isPrime = true;
      } else if (this.input > 1) {
        for (let i = 2; i < this.input; i++) {
          if (this.input % i == 0) {
            isPrime = false;
            break;
          }
        }
      } else {
        isPrime = false;
      }

      this.result = isPrime;
    },
    checkIsFibanacci() {
      console.log("checkIsFibana");
      this.result =
        this.isPerfectSquare(5 * this.input * this.input + 4) ||
        this.isPerfectSquare(5 * this.input * this.input - 4);
    },
    isPerfectSquare(input) {
      let bufferInput = parseInt(Math.sqrt(input));
      return bufferInput * bufferInput == input;
    },
  },
};
</script>

<style>
.first-column {
  max-width: 200px !important;
}
.last-column {
  max-width: 300px !important;
}
@media (max-width: 600px) {
  .scollbar {
    width: 600px !important;
    overflow-x: auto;
  }
}
</style>
