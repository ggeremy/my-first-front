<script>
    import Book from "../lib/components/Book.svelte";
    import Form from "../lib/components/Form.svelte";
    import Cart from "../lib/components/Cart.svelte";

	import { writable } from "svelte/store";

    const books = writable([]);
    let purchasedBooks = [];

    function purchaseBook(event) {
        const newBook = event.detail;
        purchasedBooks = [...purchasedBooks, newBook];
    }
    
    function addBook(newBook) {
        books.update(currentBooks => [...currentBooks, newBook]);
    }

    

</script>

<h1 class="text-3xl font-bold underline">My App</h1>

<Form submitAction={addBook}/>


<div class="flex items-center justify-center p-12">
    
    {#if $books.length > 0}
    <div class="grid grid-cols-1 gap-4 lg:grid-cols-3 lg:gap-8"> 
        {#each $books as book} 
        <Book bookTitle={book.title} bookPrice={book.price} bookDescription={book.description} on:addtocart={purchaseBook}/> 
        {/each} 
    </div>
    {:else}
    <p>No books in stock</p>
    {/if}

</div>


<Cart cart={purchasedBooks}/>


