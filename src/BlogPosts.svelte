<script>
    import {onMount} from "svelte"

    const url = "https://www.jsonstore.io/fc896abcb8b2e62999fc38366a964b3c33c0a708e0c61b9c8fde4120cb322be8";

    let results  = [];

    const getArticles = () => {
        fetch(url)
            .then(response => response.json())
            .then(data => {results.push(data.result)})
            .catch(e => console.log(e))
    };

    onMount(() => {
        getArticles();
        console.log(results)
        }
    )

    /*    const getArticles = async () => {
        const response = await fetch(url);
        results = response.json();
        console.log(results)
    };*/


   /* const getUsers = async function(){
        try{
            let response = await fetch(url);
            if(response.ok){
                let data = await response.json();
                results = data.result;
                console.log(results);
                return results
            } else {
                console.error("Une erreur serveur s'est produite :", response.status)
            }
        } catch (e){
            console.log(e)
        }
    };

results = getUsers().then()*/

</script>

<main class="blog-post__main">
    <section class="sidebar">
        <h3>Archives</h3>
    </section>

    <section class="blog--posts">
        {#each results as post}
            <div class="post--wrapper">
                <h2 class="post--title post--text">{post.title}</h2>
                <p class="post--content post--text">{post.body}</p>
            </div>
        {/each}
    </section>
</main>



<style>

    .blog-post__main {
        display: flex;
        margin : 2rem 1rem;
        border-radius: 1rem;
        min-height :400px;
    }

    .sidebar {
        width : 30%;
        border : solid 3px #e0f0ef;
        border-radius: 1rem;
        padding : 0.5rem;
    }

    .blog--posts{
    }

    .post--wrapper {
        display : flex;
        flex-direction: column;
        padding : 0.5rem 1rem;
        margin : 1rem;
        border-radius: 0.5rem;
        box-shadow: 2px 2px 5px gray;
        background: #e0f0ef;
    }

    .post--text {
        color: darkslategray;
        font-family: "Andale Mono", sans-serif;
    }

    .post--content {
        font-size: 1rem;

    }

    .post--title {
        font-size : 1.5rem;
        font-weight: 700;
    }

</style>