<script>
  export let min = 0;
  export let max = Infinity;
  export let value;
  
  // clamp value to to min if min is greater than the supplied value
  value = Math.max(value, min);

  // increment and decrement
  const decrement = _ => validateInput(value-1);
  const increment = _ => validateInput(value+1);

  // make sure it is never less than 0 and no more than the max
  const validateInput = (value) => Math.min(max, Math.max(0, Number(value)));;
</script>

<div>
  <button on:click={_ => value = decrement()}>-</button>
  <input type="number" {min} {max} bind:value>
  <button on:click={_ => value = increment()}>+</button>
</div>