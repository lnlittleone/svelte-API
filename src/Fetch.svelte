<script>
    import { onMount } from "svelte";

    const url = "https://jsonplaceholder.typicode.com/users";

    let data = [];

    const getUsers = async function(){
        try{
            let response = await fetch(url);
            if(response.ok){
                data = await response.json();
            } else {
                console.error("Une erreur serveur s'est produite :", response.status)
            }
        } catch (e){
            console.log(e)
        }
    };


    const insertPost = async (data) => {
        let response = await fetch("https://jsonplaceholder.typicode.com/posts", {
            method : "POST",
            headers : {
                "Content-type" : "application/json",
            },
            body : JSON.stringify(data)
        });
        if(response.ok){
            let post = await response.json();
            console.log(post)
        } else {
            console.error(response.status)
        }
    };

    onMount(getUsers())
</script>

{#each data as user}
    <h1>{user.name}</h1>
    <h2>{user.username}</h2>
    <h3>{user.email}</h3>
    <p>{user.address.street}</p>
{/each}