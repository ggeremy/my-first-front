<script>

    export let cart = [];
    $: total = cart.reduce( (sum, book) => sum += book.price, 0);

</script>

<div class="cart">
    <h2>Shopping list</h2>

    {#if cart.length > 0}
    <p>Total: {total}</p>
    <ul>
        {#each cart as book}
        <li>{book.title} - {book.price}€</li>
        {/each}
    </ul>
    {:else}
    <p>Your cart is empty</p>
    {/if}


</div>

<style> 
    .cart { 
      border: 1px solid #ddd; 
      padding: 1rem; 
      margin-top: 1rem; 
      border-radius: 8px; 
     } 
    ul { 
      list-style-type: none; 
      padding: 0; 
    } 
    li { 
      margin-bottom: 0.5rem; 
    } 
  </style>