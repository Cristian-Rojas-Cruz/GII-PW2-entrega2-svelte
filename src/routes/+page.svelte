<script>
  let displayValue = '';
  let result = '';

  function addToDisplay(value) {
    displayValue += value;
  }

  function clearDisplay() {
    displayValue = '';
    result = '';
  }

  function calculateResult() {
    try {
      result = eval(displayValue);
    } catch (error) {
      result = 'Error';
    }
  }
</script>

<svelte:head>
  <title>Calculator</title>
  <meta name="description" content="Simple calculator built with Svelte" />
</svelte:head>

<section class="calculator">
  <input type="text" bind:value={displayValue} readonly />
  <div class="buttons">
    <button on:click={addToDisplay.bind(null, '7')}>7</button>
    <button on:click={addToDisplay.bind(null, '8')}>8</button>
    <button on:click={addToDisplay.bind(null, '9')}>9</button>
    <button on:click={addToDisplay.bind(null, '+')}>+</button>
    <button on:click={addToDisplay.bind(null, '4')}>4</button>
    <button on:click={addToDisplay.bind(null, '5')}>5</button>
    <button on:click={addToDisplay.bind(null, '6')}>6</button>
    <button on:click={addToDisplay.bind(null, '-')}>-</button>
    <button on:click={addToDisplay.bind(null, '1')}>1</button>
    <button on:click={addToDisplay.bind(null, '2')}>2</button>
    <button on:click={addToDisplay.bind(null, '3')}>3</button>
    <button on:click={addToDisplay.bind(null, '*')}>*</button>
    <button on:click={addToDisplay.bind(null, '0')}>0</button>
    <button on:click={addToDisplay.bind(null, '.')}>.</button>
    <button on:click={calculateResult}>=</button>
    <button on:click={addToDisplay.bind(null, '/')} >/</button>
    <button on:click={clearDisplay}>C</button>
  </div>
  <p>Result: {result}</p>
</section>

<style>
  .calculator {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    margin-top: 50px;
  }

  input {
    width: 200px;
    padding: 10px;
    margin-bottom: 10px;
  }

  .buttons {
    display: grid;
    grid-template-columns: repeat(4, 50px);
    grid-gap: 5px;
  }

  button {
    padding: 10px;
    font-size: 16px;
    cursor: pointer;
  }

  p {
    margin-top: 20px;
  }
</style>