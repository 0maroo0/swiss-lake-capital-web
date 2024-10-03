<template>
  <div class="calculator">
    <h2>Investment Calculator</h2>
    <div class="slider-container">
      <label for="amount">Select Amount:</label>
      <input
        type="range"
        id="amount"
        v-model="amount"
        min="100000"
        max="100000000"
        step="100000"
        @input="calculateReturns"
      />
      <span class="amount-display">${{ amount.toLocaleString() }}</span>
    </div>
    <div class="results">
      <h3>Returns</h3>
      <div class="return-box">
        <p>
          Annual Return (17%):
          <span class="highlight">${{ annualReturn.toLocaleString() }}</span>
          per year
        </p>
      </div>
      <div class="return-box">
        <p>
          Monthly Return:
          <span class="highlight">${{ monthlyReturn.toLocaleString() }}</span>
          per month
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Calculator",
  data() {
    return {
      amount: 100000, // Default starting amount
      annualReturn: 0,
      monthlyReturn: 0,
    };
  },
  methods: {
    calculateReturns() {
      const percentage = 0.17;
      this.annualReturn = this.amount * percentage;
      this.monthlyReturn = this.annualReturn / 12;
    },
  },
  mounted() {
    this.calculateReturns(); // Calculate initial returns
  },
};
</script>

<style scoped>
.calculator {
  margin: 60px auto; /* Added vertical margin */
  width: 100%;
  max-width: 700px;
  padding: 30px; /* Increased padding for a spacious look */
  border: 1px solid #ddd;
  border-radius: 10px;
  background-color: #f9f9f9;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
}

h2 {
  text-align: center;
  color: #2947a9;
}

.slider-container {
  display: flex;
  flex-direction: column;
  margin-bottom: 20px;
}

label {
  font-weight: bold;
  color: #2947a9;
}

input[type="range"] {
  -webkit-appearance: none;
  width: 100%;
  height: 10px;
  background: #ddd;
  border-radius: 5px;
  outline: none;
}

input[type="range"]::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 20px;
  height: 20px;
  border-radius: 50%;
  background: #2947a9;
  cursor: pointer;
}

.amount-display {
  margin-top: 10px;
  font-weight: bold;
  color: #2947a9;
  text-align: center;
}

.results {
  margin-top: 20px;
  border-top: 1px solid #ddd;
  padding-top: 10px;
}

.return-box {
  background-color: #e6f0ff; /* Light background color */
  border: 2px solid #2947a9; /* Border color */
  border-radius: 5px; /* Rounded corners */
  padding: 10px; /* Padding inside the box */
  margin-bottom: 10px; /* Space between boxes */
}

.highlight {
  color: #2947a9;
  font-weight: bold;
}
/* Mobile Styles */
@media (max-width: 780px) {
  .calculator {
    max-width: 80%;
    margin: 20px; /* Reduced margin on mobile */
    padding: 20px; /* Adjusted padding */
  }

  h2 {
    font-size: 24px; /* Slightly smaller title on mobile */
  }

  input[type="range"] {
    height: 8px; /* Smaller range slider */
  }

  input[type="range"]::-webkit-slider-thumb {
    width: 15px; /* Smaller slider thumb */
    height: 15px; /* Smaller slider thumb */
  }

  .amount-display {
    font-size: 18px; /* Larger text for amount display */
  }

  .results {
    padding: 15px; /* More padding for results on mobile */
  }

  .return-box {
    padding: 15px; /* More padding inside return boxes */
  }
}
</style>
