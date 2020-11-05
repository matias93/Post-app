<script>
    import { push } from 'svelte-spa-router' 
    let urlComt = 'https://dummyapi.io/data/api/post/SFAt3mJK0qu4QOd9LgSX/comment?limit=10';
    const appId = '5fa45f13fac359660cc01b11';

    let comments = [];
    
    function getCommets() {
        fetch(`${urlComt}`,{headers:{'app-id':appId}})
           .then(data => data.json())
           .then(res => {
               comments = res.data || []
               console.log(comments)
           })
    }
  getCommets()
</script>
<div>
    {#each comments as {id, owner,message,publishDate}}
    <div class="header">
         <img  src={owner.picture} class="rounded mr-2" alt={owner.firstname}>
         <strong class="mr-auto">{owner.firstName}</strong>
         <small>{publishDate}</small>
       </div>
      <div>
        {message}
      </div>
  
    {/each}
</div>
 
   



<style>

</style>