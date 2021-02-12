<script>
  export let amount = 0;

  const validateAmount = (n) => {
    if(n > 9){
      return '9+';
    }
    return n;
  };

  // validate the amount to never be larger than 9+
  $: amount = validateAmount(amount);
</script>

<button on:click>
  <svg xmlns="http://www.w3.org/2000/svg" width="192" height="192" fill="#000000" viewBox="0 0 256 256">
    <rect width="256" height="256" fill="none"></rect>
    <path d="M192,184H68.49479a8,8,0,0,1-7.871-6.56892L33.92162,30.56892A8,8,0,0,0,26.05066,24H8" fill="none" stroke="#000000" stroke-linecap="round" stroke-linejoin="round" stroke-width="16"></path><circle cx="72" cy="204" r="20" fill="none" stroke="#000000" stroke-linecap="round" stroke-linejoin="round" stroke-width="16"></circle><circle cx="192" cy="204" r="20" fill="none" stroke="#000000" stroke-linecap="round" stroke-linejoin="round" stroke-width="16"></circle><path d="M40,64H214.4143a8,8,0,0,1,7.871,9.43108l-13.09091,72A8,8,0,0,1,201.32339,152H56" fill="none" stroke="#000000" stroke-linecap="round" stroke-linejoin="round" stroke-width="16"></path>
  </svg>
  <span class="amount">{amount}</span>
</button>

<style>
  button{
    position: relative;
    display: flex;
    align-items: center;
    justify-self: center;
    padding: 12rem;
    width: 60px;
    height: 60px;
    border: none;
    background-color: var(--color-salmon);
  }
  svg{
    width: 100%;
    height: auto;
  }
  .amount{
    --size: 25px;
    position: absolute;
    bottom: 3px;
    right: 3px;
    display: flex;
    align-items: center;
    justify-content: center;
    width: var(--size);
    height: var(--size);
    border-radius: 50%;
    background-color: var(--color-teal);
    font-size: 13rem;
  }
</style>