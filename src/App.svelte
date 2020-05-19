<script>
  import Product from './Product.svelte';
  import Button from './Button.svelte';
  import Cart from './Cart.svelte';

  let title = '';
  let price = 0;
  let description = '';

  let products = [];
  let cardItems = [];

  function createProduct() {
    const newProduct = {
      title,
      price,
      description,
    };

    products = products.concat(newProduct);
  }

  function addToCart(event) {
    const title = event.detail;
    const addProduct = products.find((product) => product.title === title)

    cardItems = cardItems.concat(addProduct);
  }
</script>

<main>
  <section>
    <div>
      <label for="title">Title</label>
      <input type="text" id="title" bind:value={title}>
    </div>
    <div>
      <label for="price">Price</label>
      <input type="number" id="price" bind:value={price}>
    </div>
    <div>
      <label for="description">Descritpion</label>
      <textarea id="description" rows="4" bind:value={description}></textarea>
    </div>

    <Button on:click={createProduct}>Create Product</Button>
  </section>

  <Cart items={cardItems} />

  {#if products.length === 0}
    <p>0 products</p>
  {:else}
    {#each products as product}
      <Product
        title={product.title}
        price={product.price}
        description={product.description}
        on:addcart={addToCart}
      />
    {/each}
  {/if}
</main>

<style>
  section {
    width: 30rem;
    margin: 0 auto;
    padding: 2rem 0;
  }

  input,
  label,
  textarea {
    width: 100%;
  }
</style>

