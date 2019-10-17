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
                article,
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
        <h2 class="wysiwyg--title text">{title}</h2>
        <p class="wysiwyg--content text">{article}</p>
    </section>

    <section class="post-form">
        <form on:submit|preventDefault={postArticle}>
            <label for="title" class="text">Titre</label>
            <input id="title" bind:value="{title}"/>

            <label for="article" class="text">Article</label>
            <textarea id="article" bind:value="{article}"></textarea>

            <button type="submit" class="button--submit text">submit</button>
        </form>
    </section>
</main>

<style>

    .text {
        font-family: Futura, sans-serif;
    }

    label {
        padding-bottom: 0.2rem;
    }

    input {
        border : solid 1px lightgray;
        border-radius: 0.5rem;
        width : 100%;
    }

    textarea {
        border : solid 1px lightgray;
        border-radius: 0.5rem;
        width : 100%;
        height: 400px;
    }

    .post-article__main {
        display : flex;
        justify-content: space-evenly;
        padding : 2rem;
    }

    .post-form {
        border : solid 3px #e0f0ef;
        border-radius: 1rem;
        padding : 1rem;
        width : 50%;
    }

    form {
        display : flex;
        flex-direction: column;
    }

    .form-wysiwyg {
        border : solid 3px #e0f0ef;
        border-radius: 1rem;
        width : 40%;
        padding : 1rem;
    }

    .wysiwyg--title {
        font-size: 1.2rem;
        font-weight: 600;
    }

    .button--submit {
        border : none;
        border-radius : 0.5rem;
        background: #72aaa7;
        color : white;
        text-transform: uppercase;
    }



</style>

