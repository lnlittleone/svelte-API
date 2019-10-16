<script>
    import {Router, Link, Route} from "svelte-routing";
    import BlogPosts from "./BlogPosts.svelte";
    import Home from "./Home.svelte";
    import PostArticle from "./PostArticle.svelte";

    export let url = "";
</script>


<Router url="{url}">
    <nav class="navbar">
        <Link to="/">Home</Link>
        <Link to="blog">Blog</Link>
        <Link to="posts">Post an article</Link>
    </nav>
    <div>
        <Route path="/" component="{Home}" />
        <Route path="blog" component="{BlogPosts}" />
        <Route path="posts" component="{PostArticle}" />
    </div>
</Router>


<style>
    .navbar {
        border-bottom : solid 1px #eaeaea;
        margin : 0;
        padding: 1rem;
        display : flex;
        justify-content: flex-end;
    }

    :global(.navbar a){
        color : #cccccc;
        font-family: "Andale Mono", sans-serif;
        font-size : 1rem;
        padding : 0 1rem;
        text-decoration : none;
    }

    :global(.navbar a:hover){
        color : #888888;
    }

</style>