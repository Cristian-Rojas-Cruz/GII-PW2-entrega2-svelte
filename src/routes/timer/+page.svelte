<script>
  let milliseconds = 0;
  let active = false;
  let intervalId;

  const startTimer = () => {
    if (!active) {
      active = true
      intervalId = setInterval(() => {
        milliseconds += 10;
      }, 10);
    }
  }

  const stopTimer = () => {
    if (active) {
      clearInterval(intervalId);
      active = false
    }
  }

  const resetTimer = () => {
    milliseconds = 0;
  }
</script>

<svelte:head>
	<title>Ejemplo 2</title>
	<meta name="description" content="About this app" />
</svelte:head>

<div class="text-column">
  <p>Tiempo transcurrido(MS): {milliseconds}</p>
  <button on:click={startTimer}>Iniciar</button>
  <button on:click={stopTimer}>Parar</button>
  <button on:click={resetTimer}>Reiniciar</button>
</div>
