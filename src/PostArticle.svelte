<script>

        let title = "";
        let article = "";

    const postArticle = async () => {
        let response = await fetch("https://www.jsonstore.io/fc896abcb8b2e62999fc38366a964b3c33c0a708e0c61b9c8fde4120cb322be8", {
            method : "POST",
            headers : {
                "Content-type" : "application/json",
            },
            body : JSON.stringify({
                title,
                body : article,
            })
        });
        if(response.ok){
            let post = await response.json();
            console.log(post)
        } else {
            console.error(response.status)
        }
    };

</script>

<main class="post-article__main">
    <section class="form-wysiwyg">
        <h2>{title}</h2>
        <p>{article}</p>
    </section>

    <section class="post-form">
        <form on:submit|preventDefault={postArticle}>
            <label for="title">Titre</label>
            <input id="title" bind:value="{title}"/>

            <label for="article">Article</label>
            <textarea id="article" bind:value="{article}"></textarea>

            <button>submit</button>
        </form>
    </section>
</main>

<style>
    .post-article__main {
        display : flex;
        justify-content: space-evenly;
    }

</style>

