<script context="module">
    // @ts-ignore
    export async function load({ fetch}){
        const res = await fetch("https://jsonplaceholder.typicode.com/posts")
        const posts = await res.json()

        if(res.ok) {
            return {
                props: {
                    posts
                }
            }
        }
        return {
            status: res.status,
            error: new Error("Could not fetch posts from JSONplaceholder")
        }
    }
</script>
<script>
    export let posts;

import HouseList from "../components/HouseList.svelte";
</script>
<div class="container mx-auto px-4">
    <HouseList posts={posts}/>
</div>