<script>
  export let min = 0;
  export let max = Infinity;
  export let value;
  
  // clamp value to min and max if value is out of range
  value = Math.min(max, Math.max(min, Number(value)));

  // increment and decrement
  const decrement = _ => validateInput(value-1);
  const increment = _ => validateInput(value+1);

  // make sure it is never less than min and no more than the max
  const validateInput = (value) => Math.min(max, Math.max(min, Number(value)));
</script>

<div>
  <button on:click={_ => value = decrement()}>-</button>
  <input type="number" {min} {max} bind:value>
  <button on:click={_ => value = increment()}>+</button>
</div>