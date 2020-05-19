<script>
  import  { createEventDispatcher } from 'svelte';
  import Button  from './Button.svelte';

  export let title;
  export let price;
  export let description;

  const dispatch = createEventDispatcher();

  function addToCart() {
    dispatch('addcart', title);
  }
</script>

<div>
  <h1>{title}</h1>
  <h2>{price}</h2>
  <p>{description}</p>
  <Button on:click={addToCart}>Add to cart</Button>
</div>

<style>
  div {
    margin: 1rem;
    box-shadow: 0 2px 8px  rgba(0, 0, 0, 0.26);
    padding: 1rem;
    border-radius: 5px;
    background-color: white;
  }

  h1 {
    font-size: 1.25rem;
    margin: 0.25rem 0
  }

  h2 {
    font-size: 1rem;
    margin: 0.25rem 0;
    color: #4B4B4B;
  }

  p {
    margin: 0.25rem 0;
  }
</style>

