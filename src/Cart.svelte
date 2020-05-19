<script>
  export let items;
</script>

<style>
  ul {
    list-style: none;
    margin: 1rem;
    padding: 0;
  }

  li {
    margin: 0.5rem 0;
    padding: 0.5rem;
    border: solid 1px #CCCCCC;
  }

  h1 {
    font-size: 1.15rem;
    margin: 1rem;
  }
</style>

<ul>
  {#each items as item}
    <li>{item.title} - {item.price}</li>
  {/each}
</ul>

<h1>Total $ __,__</h1>
