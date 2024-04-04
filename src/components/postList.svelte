<script>
    import { onMount } from "svelte";
    let posts =[]


    onMount(async () => {
        const response = await fetch('https://jsonplaceholder.typicode.com/posts');
        posts = await response.json();
        console.log(posts);
    });

  
</script>



{#each posts as post (post.id)}

   <h2 class="text-3xl my-10">{post.id}. {post.title}</h2> 
    <p class="text-white">{post.body}</p>
    <hr />
{/each}