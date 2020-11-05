<script>
  import Loading from '../Component/Loading.svelte';
  import Posts from './Posts.svelte';

  const url = 'https://dummyapi.io/data/api/user/0F8JIqi4zwvb77FGz6Wt/post?limit=10'
  const appId = '5fa45714ba2bf438452497698';
  let promise = getPosts();
  let posts = [];

  async function getPosts(){
      const resp = await fetch(`${url}`,{headers: {'app-id': appId} })
      posts = await resp.json()
      if(resp.ok){
          console.log(posts.data)
          return posts.data
      }else {
          throw new Error('no se puede traer la lista de posts')
      }
  }
 </script>

<h1 class="title">Lista de Posts</h1>
{#await promise}
    <div class="center">
        <Loading/>
    </div>
{:then posts} 
    <Posts {posts}/>
{/await}


<style>
    .title {
        text-align: center;
        margin-top: 30px;
        color: #fff;
    }
</style>