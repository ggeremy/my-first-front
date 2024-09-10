<script>
    export let submitAction;

    let title = '';
    let price = 0;
    let description = '';

    function handleSubmit(event) {
        const newBook = {
            title, 
            price,
            description
        };

        submitAction(newBook);

        title = '';
        price = 0;
        description = '';
    }
</script>


<div class="flex items-center justify-center p-12">

    <div class="mx-auto w-full max-w-[550px]">
      <form on:submit|preventDefault={handleSubmit}>
        <div class="mb-5">
          <label
            for="title"
            class="mb-3 block text-base font-medium text-[#07074D]"
          >
            Title
          </label>
          <input
            type="text"
            id="title"
            placeholder="Title"
            bind:value={title}
            class="w-full rounded-md border border-[#e0e0e0] bg-white py-3 px-6 text-base font-medium text-[#6B7280] outline-none focus:border-[#6A64F1] focus:shadow-md"
          />
        </div>
        <div class="mb-5">
          <label for="price" class="mb-3 block text-base font-medium text-[#07074D]">Price</label>
          <input
            type="number"
            id="price"
            bind:value={price}
            placeholder="Price"
            class="w-full rounded-md border border-[#e0e0e0] bg-white py-3 px-6 text-base font-medium text-[#6B7280] outline-none focus:border-[#6A64F1] focus:shadow-md" required/>
        </div>

        <div class="mb-5">
          <label
            for="description"
            class="mb-3 block text-base font-medium text-[#07074D]"
          >
            Description
          </label>
          <textarea
            rows="4"
            id="description"
            placeholder="Type in a book description"
            bind:value={description}
            class="w-full resize-none rounded-md border border-[#e0e0e0] bg-white py-3 px-6 text-base font-medium text-[#6B7280] outline-none focus:border-[#6A64F1] focus:shadow-md"
          ></textarea>
        </div>
        <div>
          <button 
            type="submit"
            class="hover:shadow-form rounded-md bg-blue-700 hover:bg-blue-800 py-3 px-8 text-base font-semibold text-white outline-none">
            Submit
          </button>
        </div>
      </form>
    </div>
  </div>