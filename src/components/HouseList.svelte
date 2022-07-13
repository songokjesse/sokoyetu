
<script>
   export  let posts;
</script>
<div class="form-group">
    <input 
    name="search" 
    type="text" 
    placeholder="Search for House"
    class="form-control input input-bordered w-full"
    />
</div>

<h1>House List</h1>
<ul>
    {#each posts as post}
            <li>{post.title}</li>
    {/each}
</ul>