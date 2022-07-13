
<script>
   export  let posts;
   let searchQuery = ""
   $: searchedQuery = posts.filter((post) => {
       return post.title.includes(searchQuery)
   })
</script>
<div class="form-group">
    <input 
    name="search" 
    type="text" 
    placeholder="Search for House"
    class="form-control input input-bordered w-full mt-4"
    bind:value={searchQuery}
    />
</div>
<div class="mt-5">
    Houses: {searchedQuery.length}
</div>
<div class="divider"></div>
    {#if searchedQuery.length}
        <div class="overflow-x-auto mt-4">
            <table class="table w-full">
                <tbody>
                <!-- row 1 -->

        {#each searchedQuery as post}
            <tr class="hover">
                <td>
                    <input type="checkbox" value="{post.id}">  {post.title} <br/>
                </td>
            </tr>
        {/each}
                </tbody>
            </table>
        </div>
    {:else }
        <h3 class="alert-warning">No results found for "{searchQuery}"</h3>
    {/if}
