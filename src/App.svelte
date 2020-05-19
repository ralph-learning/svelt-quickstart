<script>
  import Product from './Product.svelte';
  import Button from './Button.svelte';

  let title = '';
  let price = 0;
  let description = '';
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

    <Button>Create Product</Button>
  </section>

  <Product
    title={title}
    price={price}
    description={description}
  />
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

